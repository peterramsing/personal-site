---
layout: post
title: LostGrid to no longer support older versions of Node
permalink: lostgrid-node-versions
date: 2016-11-09 12:00:00
description: Some notes about LostGrid and Node versions.
keywords: frontend, lostgrid, grid, css
social_title: LostGrid to no longer support older versions of Node
social_image: /img/posts/lostgrid-node-support.jpg
social_description: Some notes about LostGrid and Node versions.
excerpt_separator: <!--more-->
---

## LostGrid is going to drop support for Node v0.10 and v0.12

Okay okay...not just yet. But I'm releasing a [patch today](https://github.com/peterramsing/lost/releases/tag/v7.1.1) that will start to put warnings out there about the drop of Node support in Version 8. Version 8 isn't quite ready yet and I'm going hold off releasing it until December when Node support for v0.12 ends.

Moving forward, LostGrid is going to support Node versions according to the Node LTS docs. [See Docs here](https://github.com/nodejs/LTS#lts-schedule)

<!--more-->

### What's this mean?
This means that LostGrid, after v8, will probably work...until it doesn't. I'll announced when the Node v0.10 and v0.12 tests don't pass anymore and be sure to keep the community in the loop, though! I've gotten a lot of support for dropping older versions of Node so I'm feeling confident that this should be alright.

<p style="text-align: center;">
  <img src="{{ site.baseurl }}/img/posts/lostgrid-node-support.jpg" alt="">
</p>


### What if I need to support older versions of Node?
Probably don't update to v8. ...or, when you hear the tests aren't passing anymore freeze your version. But I'm considering even patch releases to break on v0.10 or v0.12 as totally valid as it's "not officially supported". ...and who knows, I might even have v8 break in Node v0.10 or v0.12 right away. I'm just now starting to write code that might break it so whether it's right away or in a little...it will happen. I'm sorry. 😬

### Great! ...can I get some LostGrid swag, too?
I'm actually making some LostGrid shirts soon...so yes! You can get some swag! Be looking for them soon! (and stickers too!)

### I to share my thoughts!
Please do! Feel free to communicate through the ways below: (and thanks!)

- [@LostGrid](https://twitter.com/lostgrid) on Twitter
- [Gitter](https://gitter.im/peterramsing/lost)
- [Submit and issue](https://github.com/peterramsing/lost/issues/new).
