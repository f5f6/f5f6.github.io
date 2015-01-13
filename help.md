---
layout: page
title: Help
author: Leo
---

- *
{:toc}

# 编写指南

这个blog使用 [Jekyll](http://jekyllrb.com/) 静态网站生成工具生成。原始文件在 [f5f6.github.io](https://github.com/f5f6/f5f6.github.io) 项目中。

## 发表与修改

要发表一篇新日志，在 `_posts` 目录里新建一个文件，遵循 `YYYY-MM-DD-name-of-post.md` 的命名规则，并参考其他日志，在正文最开始处放置正确的头信息。

如要修改已有日志，编辑相应 markdown 文件即可。

## 生成与预览

网站生成在 GitHub 上进行，每次 git push 到 GitHub 会自动触发重新生成。但建议在本地安装 Jekyll，先在本地预览效果后再提交。

Jekyll 安装与运行方法请参考 [GitHub Using Jekyll with Pages](https://help.github.com/articles/using-jekyll-with-pages/) 的 Installing Jekyll 和 Running Jekyll 部分。为简化Windows平台下的使用，已经自带了一个 all-in-one 的 Jekyll 可执行程序，双击执行`_bin\preview.bat`即可。

# Markdown语法

这个blog使用的markdown解释器是[kramdown](http://kramdown.rubyforge.org/quickref.html)，比起标准markdown有所增强。再加上Jekyll的一些插件特供的特殊功能。

## 通用语法

### 标题

标题用`#`开头，一个井号是一级标题，两个井号是二级标题，井号越多字体越小。

### 链接

格式：

    [text](link)

### 图片

与链接类似，区别是前面增加叹号`!`：

    ![text](link)

另一种图片语法是由插件支持的，用`{` `%`包围的img标签，后面跟着图片URL，在URL前可以加入可选的css class名称，如：`left`, `right`，得到文字环绕效果。

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

- - - -
