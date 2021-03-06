---
layout: page
title: About F5F6
permalink: /about.html
---

# 序

## 工程师文化

f5f6的一个初衷是希望能通过技术博客，唤醒工程师们的自我驱动力，对编程的爱好，对技术的兴趣，对学习的热爱。最好能得到老板们的鼎力支持。

在公司的层面上，我们没有996的文化，有宽松的环境，有开放的思想，有Google推崇的20%的自由时间，有脑洞打开的黑客松创新活动。然而这些在项目进度的鞭打下，却变得不那么实际。

在团队层面上，团队越来越大了，但文化底蕴逐渐消亡。在进度敲打的背景下，技术分享日渐式微，测试渐渐偏移自动化轨迹，Code Review变得简化且简陋，对技术的追求不再那么热切。有甚者连“工程师的自我修养”都丢弃了，只能默默背书。 

敏捷面向了管理，而不再是自治的团队。缺少了回顾与展望，只能周而复始的盘旋而不能迭代上升。

也许言之过甚，但底线是工程师的自我修养不能丢，工程师的文化应要有。希望程序猿们能多写点日志，沉淀下技术积累，对团队和社区多点贡献。也希望构建一个带有浓重工程师文化色彩的团队，来驱动产品的演进和技术的发展。


## 加入我们 ##

f5f6旨在汇聚一些技术相关的干货，包括但不仅限于开发，测试，运维。参考下面的内容策划，愉快的分享内容。

如果你有Github的账号，请告诉@[KasperDeng](https://github.com/kasperdeng)。


## 内容策划 ##

既可以分享日常看到的技术资料与资讯。 放到对应板块，直接提交即可。也将自己原创的日志分享给大家，形成一个f5f6日志的大聚合。

推荐做法是先在自己平常写日志的地方写好日志，然后在f5f6里新建一个日志，复制粘贴日志的开头摘要，然后附加一个链接到你写好的日志。
f5f6项目, 及开发日志，向大家怒刷存在感或招徕伙伴。

编辑们会定期发送整理后续版面与内容。


# 编写指南

这个blog使用 [Jekyll](http://jekyllrb.com/) 静态网站生成工具生成。原始文件在 [f5f6.github.io](https://github.com/f5f6/f5f6.github.io) 项目中。

## 发表与修改

要发表一篇新日志，在 `_posts` 目录里新建一个文件，遵循 `YYYY-MM-DD-name-of-post.md` 的命名规则，并参考其他日志，在正文最开始处放置正确的头信息。

如要修改已有日志，编辑相应 markdown 文件即可。

## 生成与预览

网站生成在 GitHub 上进行，每次 git push 到 GitHub 会自动触发重新生成。但建议在本地安装 Jekyll，先在本地预览效果后再提交。

* Jekyll 安装与运行方法请参考 [GitHub Using Jekyll with Pages](https://help.github.com/articles/using-jekyll-with-pages/) 的 Installing Jekyll 和 Running Jekyll 部分。
* 为简化Windows平台下的使用，已经自带了一个 all-in-one 的 Jekyll 可执行程序，双击执行`_bin\preview.bat`即可。

## 草稿

* 为了避免没有写完的草稿发布出去，新日志应该先放在 `_drafts` 目录中，待完成后才移动到 `_posts` 目录。
* Draft 中的文件不会在 GitHub 上生成内容，仅当在本地预览时用 `jekyll serve --drafts` 命令才能看到。
* 如果是 Windows 用户，使用 `_bin\preview.bat` 即可。

## 内容整理与归类
* 原创博客，请添加在正文最开始处添加`tags`头信息，例如`tags: [docker]`。所有标签会在[tags](/tags.html)页面自动分类。
* 引用文章，管理员会在[内容索引](/all.html)下手工整理分类。
* 电子书籍，请添加到`topic/book.md`。
* 热门技术，请添加到`topic/pop.md`。
* 工具推荐，请添加到`topic/tool.md`。

# Markdown语法

这个blog使用的markdown解释器是[kramdown](http://kramdown.rubyforge.org/quickref.html)，比起标准markdown有所增强。再加上Jekyll的一些插件特供的特殊功能。

## 通用语法

### 标题

标题用`#`开头，一个井号是一级标题，两个井号是二级标题，井号越多字体越小。

### 链接

文字链接：

    [text](link)

直接显示链接：

    <link>

### 图片

与链接类似，区别是前面增加叹号`!`：

    ![text](link)



### 引用 (blockquote)

用`>`开头的一个段落：

> Stay hungry...
stay foolish.

用四个空格缩进的段落，会按原始格式显示，相当于HTML的`<pre>`的效果：

    +----+
    |    |
    +----+

也可以通过在原始格式引用段落的前后各加一行波浪号`~~~~~~`来实现。(这是kramdown特有的语法)

### 字体变化

用`*`或`_`包围的文字会用 *斜体* 显示。

如果双重符号`**`或`__`则会用 **粗体** 显示。

用`` ` ``包围的文字按代码格式`code`显示。

### 列表

用`*`, `+`, `-`开头的行都会作为列表项。子项缩进两个空格。

+ 加号开头的段落
  + 缩进两个空格，加号开头
    + 再缩进两个空格，三级项目
- 其次

### 分割线

    ---

## 增强功能

### 解释列表

~~~~
名词1
: 解释

名词2
: 解释

  另一个段落继续解释。
~~~~

显示效果：

名词1
: 解释

名词2
: 解释

  另一个段落继续解释。

### 表格

注意第二行的分割线的冒号位置，决定了这一列的对齐方式。

    No.   | Name    | Status  |
    -----:|:--------|:-------:|
    1     | Alaph   | done    |
    2     | Beta    | ongoing |
    10000 | Release | n/a     | 

效果：

No.   | Name    | Status  |
-----:|:--------|:-------:|
1     | Alaph   | done    |
2     | Beta    | ongoing |
10000 | Release | n/a     | 


### 脚注

增加脚注[^1]很简单，就是这样：`[^1]`

脚注定义的写法是以`[^1]: `开头，后面跟着定义。

[^1]: 脚注一定会显示在最末尾。

### 目录

在文章开头加上以下两行，生成目录。

{% raw %}
    - *
    {:toc}
{% endraw %}

### 嵌入代码

这个blog是由Github在线生成的，Github只支持使用pygments做语法彩色渲染，但pygments需要依赖python，本地环境配置依赖多，不是所有人都有完整的本地环境做预览，因此本blog关闭了语法高亮功能，请勿使用`highlight`标签，否则可能会造成别人本地预览失败。

如要嵌入代码片段并希望有好的显示效果，建议将代码片段保存在[gist](https://gist.github.com/)并使用`gist`标签：

{% raw %}
    {% gist parkr/c08ee0f2726fd0e3909d %}
{% endraw %}


### 设置内容的Html属性

在一种元素类型如普通文字，链接后面，用`{:attributeKey=attributeValue}` 定义

    A [link](test.html){:style='color:red'}

# 成员信息

每个成员需要在`_data/members.yml`里面注册自己的信息，这些信息会显示在 [Members](/members/) 页面里面。

成员信息的模板如下：

~~~
- name: Calvin
  github: calvinxiu
  description: >
    开源项目 [SpringSide](http://springside.io/) 维护者，江湖人称江南白衣。
  links:
  - url: http://anywhere.com
  - name: SpringSide
    url: http://springside.io
  - type: 新浪微博
    name: calvin1978
    url: http://www.weibo.com/calvin1978     
~~~

`name`为成员在这个blog里的名字，需要与 post author 里用的相同。`github`是github中的用户名（不是邮箱），必须提供。`description`为可选的个人描述，可以嵌入markdown语法。`links`下面列出个人的相关网站链接，每个链接有 type, name, url 三个属性，`url`为必须，其他可选。 编辑时要小心，`-`表示一个链接，不要多加了。

- - - -
