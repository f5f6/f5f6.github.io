---
layout: post
title:  "客户端收到了正确的返回结果, 但是系统还是报socket timeout"
author: sean.gong
date:   2015-01-27
category: blog
---

###现象
最近客户的site上遇到一个问题, 一个web  services 的请求已经收到了正确的响应. 但是日志中不停的报"java.net.SocketTimeoutException: Read timed out". 但是在实验室里面没有办法重现. 最后发现请求是HTTP 1.0, 回的响应是HTTP 1.1. 最后将请求改成HTTP1.1, 问题解决.(感谢 Geoffrey Chen 提供)

###原因分析
- 从客户端看,客户端使用HTTP 1.0发送request同时接到了HTTP1.1格式的response, 并按照response里面的内容发送ACK应答, 但是底层的TCP连接则需要响应FIN,ACK, 从而按照HTTP1.0的规范关闭请求;

- 从服务端看,他按照HTTP1.1处理, 当他接收到ACK后,就没有任何响应,自动结束对话. 

- 因此默认60秒后客户端超时发送强制关闭连接。

![tcpdump](/attachments/201501/http10-11_mix_issue.png)
	
###解决方法
问了一下google，发现这个问题只是会在aixs 1.4 实现的服务器才有问题。

- 使用相同的HTTP规范

- 继续使用HTTP1.0

```
((TerminalSessionSOAPBindingStub) terminalSession_PortType)._setProperty(
        MessageContext.HTTP_TRANSPORT_VERSION, HTTPConstants.HEADER_PROTOCOL_V10);
```

###useful link
[http://samaxes.com/2009/04/axis-14-read-timed-out-and-http-11/](http://samaxes.com/2009/04/axis-14-read-timed-out-and-http-11/)


####参考：TCP连接/断开流程

![tcp_connect](/attachments/201501/tcp_connect.gif)

