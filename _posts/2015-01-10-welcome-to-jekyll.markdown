---
layout: post
title:  "How to write in this blog"
author: aleung
date:   2015-01-10 00:47:48
tags: [blogging]
---

- .
{:toc}

## Install Jekyll

You could write and edit posts without installing Jekyll on your computer. Just edit the markdown files in `_posts` directory. However with Jekyll you're able to preview the site.

Please follow the guide in [GitHub Help: Using Jekyll with Pages](https://help.github.com/articles/using-jekyll-with-pages/) to install Jekyll.

## Add New Post

You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

# Markdown Syntax

Check markdown source of this post for the syntax.

{% highlight ruby %}
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
{% endhighlight %}

# Issues

This new Jekyll site is just initialized. A lot of things need to be worked on. Please report bugs or feature requests to the [issue board](https://github.com/f5f6/f5f6.github.io/issues).
