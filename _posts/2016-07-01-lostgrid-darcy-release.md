---
layout: post
title:  LostGrid, the new Darcy Release
permalink: lost-grid-darcy-release
date: 2016-07-01 23:50:00
description: LostGrid releases new version called Darcy
keywords: PostCSS, CSS, frontend, front-end, lostgrid, lost, grid, software-release
social_title: LostGrid, the new Darcy Release
social_image: img/lostgrid-darcy.png
social_description: The latest version of LostGrid, the Darcy Release, comes with a new lost-row feature and several bug fixes.

---
<a href="https://twitter.com/share" class="twitter-share-button" data-url="http://peter.coffee/lost-grid-darcy-release" data-text="LostGrid releases the latest version targeting bug fixes and a new feature for lost-row." data-via="LostGrid" data-related="peterramsing">Tweet</a> <script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+'://platform.twitter.com/widgets.js';fjs.parentNode.insertBefore(js,fjs);}}(document, 'script', 'twitter-wjs');</script>

## LostGrid, the Darcy Release
Tonight I released the [latest version](https://github.com/peterramsing/lost/releases/tag/v7.0.1) of the [open source project](https://github.com/peterramsing/lost), LostGrid I maintain. The main focus of this release was to fix some bugs that caused some breaking changes, start a new version naming strategy, add a feature for `lost-row` and to also ensure that there was movement on the project.

<h2 id="what-changed"><a href="#what-changed">What changed?</a></h2>
[Changelog](https://github.com/peterramsing/lost/releases/tag/v7.0.1)

* [#306](https://github.com/peterramsing/lost/pull/306) [FEATURE] lost-row: none; was added to reset the element back to default settings.
* [#297](https://github.com/peterramsing/lost/pull/297) [BUGFIX] Updates the clear: left; to be clear: both; for lost-column/waffle rule.
* [#299](https://github.com/peterramsing/lost/pull/299) [BUGFIX] Changes the size from 99.99/999999% to 99.9% within lost-column, lost-masonry-column, lost-move, lost-offset, lost-row and lost-waffle. This is because in Edge and IE there were some rounding errors causing stacking of columns instead of allowing them to sit side-by-side.
* [#251](https://github.com/peterramsing/lost/pull/251) [REFACTOR] Minor refactor to add in cloneAllBefore function to make readability easier.

<h2 id="what-breaking-changes-are-there"><a href="#what-breaking-changes-are-there">What breaking changes are there?</a></h2>
* In order to add the clearing in a more standard way by using "both" it required that the preferred method of `clear: both;` be the default. A global setting was added to set this back to left if your project needs it. `@lost clearing left;` will keep you going if your project is affected by this change.
* Thanks to [Jon](https://github.com/dotnetCarpenter) LostGrid now has a [math based](https://github.com/peterramsing/lost/pull/296#issuecomment-222321312) approach to the 99% rounding. This might cause issues in your project but after testing in a number of different browsers it appears to be a non-issue. It's recommended that you just peruse your project with the oldest version of IE that you support to ensure there isn't an edge case that you're caught in.

![Image of the LostGrid character looking at a map.]({{ site.baseurl }}/img/lostgrid-darcy.png)

## What's with Darcy? Why not just Version 7?
Great question! To answer it we need to understand the importance of [semver](http://semver.org/). In order to progress LostGrid there are going to have to be breaking changes. The nature of how LostGrid was initially written means that as it matures there is going to be a phase of breaking changes. So V8 and V9 will be coming because **I just don't have time to bunch all those breaking changes into one version without holding back needed features and bug fixes.**

So, Darcy release will be here for a while. Darcy will probably be around for several major version numbers. When a new set of features come out and it starts to not feel like the Darcy release anymore then it'll change. But it's just for marketing. As the plugin progresses we'll be able to talk about it using these terms.

This thought process was inspired by this [talk](https://youtu.be/tc2UgG5L7WM) on semver from JSConf.

Oh, and "[Mr. Darcy](https://en.wikipedia.org/wiki/Mr._Darcy)" is a beloved character of mine from the author Jane Austen.

## Something's broken!
If you're experiencing any issue with the Darcy Release please feel free to reach out via [@LostGrid](https://twitter.com/lostgrid) on Twitter, [Gitter](https://gitter.im/peterramsing/lost) or [submit and issue](https://github.com/peterramsing/lost/issues/new).

**Thanks to [everyone](https://github.com/peterramsing/lost/graphs/contributors) that's made this project possible!**
