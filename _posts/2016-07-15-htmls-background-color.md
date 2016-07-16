---
layout: post
title: HTML's Background Color and Overscroll
permalink: htmls-background-color
social_title: HTML's Background Color and Overscroll
date: 2016-07-15 23:00:00
description: A quick web tip on overscroll background color.
social_description: A quick web tip on overscroll background color.
keywords: css, web development, html, design, branding, overscroll, background color
---

<a href="https://twitter.com/share" class="twitter-share-button" data-text="A quick tip on overscroll color" data-url="http://peter.coffee/htmls-background-color" data-show-count="false">Tweet</a><script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<style>
  button:focus {
    outline: none;
  }
  .post-content img {
    margin-top: 0;
  }

  .gif-figure {
    text-align: center;
  }

  @media (min-width: 600px) {
    .gif-figure {
      width: 50%;
      float: left;
    }
  }
</style>

Here's a little tip if you're working on a site who's header and footer are the same color.

*click on the gifs to play, click again to stop*

<div class="utl-clearfix">
  <figure class="gif-figure">
    <img data-gifffer="{{ site.baseurl }}/img/scroll-past-sad.gif" alt="The not-happy version of scrolling past a header that leaves behind it a white break." />
    <figcaption>When overscrolling (rubber-banding) it can show the non-header/footer color.</figcaption>
  </figure>

  <figure class="gif-figure">
    <img data-gifffer="{{ site.baseurl }}/img/scroll-past-glad.gif" alt="The happy version of scrolling past a header that doesn't leave behind the white bar." />
    <figcaption>Now it feels a bit more, dare I say, native?</figcaption>
  </figure>
</div>


## How to do this:

{% highlight css %}
html {
  background-color: $header-footer-color;
}

body {
  background-color: $maybe-white;
}
{% endhighlight %}

For me, I just sort of have forgotten about the `html` element and how it can be styled. It's not game changing but if it fits for your site it can make a designer's day.

Here's a [gist](https://gist.github.com/peterramsing/d3ba8502730471691f73361f0490a185#file-overscroll-html-L59) with some example code.

Here's a [live version]({{ site.baseurl }}/static/example/overscroll.html) version of that example code.

## Here are two examples of this for [Dell](http://www.dell.com/en-us/) and [Moz](https://moz.com/).

<div style="text-align: center">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/ikfcFfn23Kk" frameborder="0" allowfullscreen></iframe>
</div>

## Where does this work?

I tested this in the latest versions of Chrome, Safari, and Opera. Firefox and IE don't do "overscroll".


<script type="text/javascript" src="{{ site.baseurl }}/js/gifffer.min.js"></script>

<script>
window.onload = function() {
  Gifffer();
}
</script>
