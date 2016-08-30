---
layout: post
title:  New LostGrid release 7.1.0
permalink: lostgrid-darcy-7-1-0
date: 2016-08-29 14:50:00
description: New LostGrid Darcy release with feature enhancements and a major under-the-hood refactor.
keywords: PostCSS, CSS, frontend, front-end, lostgrid, lost, grid, software-release
social_title: New LostGrid version 7.1.0
social_image: img/lostgrid-darcy.png
social_description: LostGrid's latest version of Darcy 7.1.0 comes with a new utility feature and refactored core using Airbnb's ESLint configuration

---
<a href="https://twitter.com/share" class="twitter-share-button" data-url="{{ page.url | prepend: site.url }}" data-text="{{ page.description }}" data-via="LostGrid" data-related="peterramsing">Tweet</a> <script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+'://platform.twitter.com/widgets.js';fjs.parentNode.insertBefore(js,fjs);}}(document, 'script', 'twitter-wjs');</script>


<h2 id="what-changed"><a href="#what-changed">What changed?</a></h2>
[Changelog](https://github.com/peterramsing/lost/releases/tag/v7.1.0)


* [#322](https://github.com/peterramsing/lost/pull/322) [FEATURE ENHANCEMENT] There is a new ability to add an `rgb` color value to `lost-utility: edit;` to customize your editing color. `lost-utility: edit rgb(60, 0, );`
* [#324](https://github.com/peterramsing/lost/pull/324) [REFACTOR] LostGrid's core is now written to follow the [airbnb](https://github.com/airbnb/javascript) javascript styleguide with ESLint linting along the way.

I've missed diving into code like I used to. This is a minor release adding a little feature enhancement for `lost-utility`. There are some cases where you might want to have different colors used in the `edit` mode of `lost-utility`. Now you can add in an `rgb` value. When I went to bed after hitting "release" last night I realized that I should probably also add in some color variables as well like "blue" and "red" etc. Because I'm converting it to `rgba` I don't think it would be as simple as accepting valid `css` colors but that's certainly something that could be in the cards.

I've been wanting to get my hands deep into the core of LostGrid for some time. The refactor to match airbnb's javascript style guide was a great excuse. I'm really happy with how it all turned out and I feel even more confident in the codebase. A goal since taking over LostGrid was to focus on stability. I ran into some node issues having ESLint be a part of the build process and I didn't want to delay this release any longer so I shipped without it: but that will be coming soon.

Coming in the next release is, by popular demand, the updating of the `lost-offset` rule to be a little more intuitive. (See issue [184](https://github.com/peterramsing/lost/issues/184)) This is slated for version 8 and I'm excited about what other things I can put in that version. As I mentioned in my [last post](/lost-grid-darcy-release) regarding the release of LostGrid, I'm not focused on the versions being used for marketing. That's why it's called the Darcy release. When it feels like a large enough change to change the name then the name will be chanted. I really value semver and want LostGrid to be really trusted codebase so major versions might come more quickly than the "marketing" might dictate.

With any large breaking changes I'll be sure to have upgrade paths in place to help codebases take advantage of the new versions like I did in the [last major release](/lost-grid-darcy-release#what-breaking-changes-are-there).

![Image of the LostGrid character looking at a map.]({{ site.baseurl }}/img/lostgrid-darcy.png)


## Something's broken?
If you're experiencing any issue with the Darcy Release please feel free to reach out via [@LostGrid](https://twitter.com/lostgrid) on Twitter, [Gitter](https://gitter.im/peterramsing/lost) or [submit and issue](https://github.com/peterramsing/lost/issues/new).

**Thanks to [everyone](https://github.com/peterramsing/lost/graphs/contributors) that's made this project possible!**
