---
layout: post
title: How to add gradients to images with CSS&nbsp;::after
permalink: how-to-use-css-pseudo-elements-to-add-a-gradient-to-images
social_title: How to add gradients to images with CSS ::after
date: 2016-07-23 16:00:00
description: Adding a linear-gradient to images is rather easy and can be adapted to create a variety of design enhancements.
social_description: How to add a linear-gradient to images using the ::after pseudo-element for subtle but awesome design enhancements.
keywords: css, pseudo-elements, after, html, frontend, gradients
social_image: /img/css-after-pseudo-element-gradient-example.jpg
category: development
excerpt_separator: <!--more-->

---

If you're wanting to add a gradient to an image I have found a lot of posts that explain how to do it with [background images](https://css-tricks.com/tinted-images-multiple-backgrounds/). This has been the go-to strategy of mine for a while but I thought it didn't feel *quite* right for every case.

![Gradient on image example]({{ site.baseurl }}/img/css-after-pseudo-element-gradient-example.jpg "Gradient on image example")

<!--more-->

In order to help keep a codebase maintainable the background image solution didn't seem like the best solution. Whenever possible I want to keep my content in the `html` and the styles in the `css`. I don't feel like that is what the `background-image` property is for. If an image is a part of the content and not the background, separation of concerns says to put the image in the `html`.

## ::after css pseudo-element

When I needed to add a gradient on an image this week I decided to get a cup of [coffee*](#coffee-break) and think about it for a minute before going with the `background-image` approach. The quick ponder paid off as I sat back down to try what came to mind. `::after`

## TL;DR The How To

I created a [CodePen](http://codepen.io/peterramsing/pen/jAxVBB/) but thought I'd explain some things here.

* You need to surround the `<img />` tag with a `<div>`. This is because presently, the [CSS spec](https://www.w3.org/TR/CSS21/generate.html#before-after-content) doesn't specify how exactly the `::after` interacts with replaced elements and the `img` is a replaced element.
* This isn't supported before IE 10 or below. [caniuse linear-gradient](http://caniuse.com/#search=linear-gradient)
* You can do a lot with that `linear-gradient`. Using multiple color stops will give you a lot of flexibility.
* To adapt for different size layouts you might need to add those breakpoints in and adjust the height of the `::after`.

### Q/A:

* `::after` vs `:after`: If you're referring to content, `::` should be used. `after` and `before` are examples of content whereas `active` or `hover` aren't content. The `::` is supported above IE8 but if you need IE8 support you can't use `linear-gradient` and thus all this is for not. I understand...IE must be supported in some cases. Your pain is real.
* `::after` vs `:before`: You could do this with a `before` but `after` feels right here. If you want a gradient from the top then `before` would be perfect. Adapt this to your needs.

<br/>

<p data-height="572" data-theme-id="0" data-slug-hash="jAxVBB" data-default-tab="css,result" data-user="peterramsing" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/peterramsing/pen/jAxVBB/">Adding a Gradient to an Image using ::after</a> by Peter Ramsing (<a href="http://codepen.io/peterramsing">@peterramsing</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>


<div class="footnotes">
  <p class="footnote" id="coffee-break">* I recently joined the <a href="https://www.wework.com/locations/portland/custom-house" rel="nofollow">Portland WeWork</a> and they have ready-made coffee. #awesome</p>
</div>
