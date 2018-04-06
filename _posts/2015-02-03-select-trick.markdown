---
layout: post
author: Samuel Ma
title: "你还在用Select吗"
tags: [Linux]
---

select()经常作为deMultiplex的分发者，也是reactor模式的重要部分，在编程中会经常遇到，当然java io 编程是不会直接touch到这一部分的。

问题来源于我们的一段JNI的c代码，主要是做sctp的socket编程的，这段JNI代码是在weblogic容器里面被调用。现象是在weblogic容器里面这段c代码表现异常，甚至导致jvm crash。

[全文閱讀](http://eyinsma.github.io/tech/2015/01/31/%E8%BF%98%E5%9C%A8%E7%94%A8select%E4%B9%88)
