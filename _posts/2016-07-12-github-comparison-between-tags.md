---
layout: post
title: Comparison Between Tags on GitHub
permalink: github-comparison-between-tags
social_title: Comparison Between Tags on GitHub, Do you need to compare between two different tags?
date: 2016-07-12 09:00:00
description: Comparing between two versions using the GitHub compare tool
social_description: Need to compare different versions on GitHub?
social_image: /img/github-compare-page.png
keywords: github, git, diff, compare, changelog, normalize, peter ramsing, tips
audio: comparison-between-tags-on-github
category: development
---

Often I'll want to see the difference between two releases on GitHub. Typically there is a CHANGELOG that will tell me a between versions but what if I want to see a diff between two versions that aren't sequential? GitHub offers a way to do this.

I've been adding a link to the actual code diffs between versions in my [LostGrid Changelist](https://github.com/peterramsing/lost/releases/tag/v7.0.3) for each release and I haven't seen many other examples of this.

Today I needed to see the diff between our current version or [normalize.css](https://github.com/necolas/normalize.css/) and the latest version. Because we were behind a few versions it wasn't as simple as looking at the [CHANGELOG.md](https://github.com/necolas/normalize.css/blob/master/CHANGELOG.md) so I used the `compare` tool. It's same place you would go to create a Pull Request but it also allows you to compare between tags. I find it easiest is to use the `URL` to perform the comparison.

## So how?

https://github.com/`user`/`repo`/`beginning-tag`...`ending-tag`

The key is that "..." and knowing the tags. I typically start at the release page and go from there. The GIF below explains it. 👍🏻

<figure>
  <img src="{{ site.baseurl }}/img/normalize-compare-url-closeup.png" class="image--full-width" alt="image of github url with compare and the ">
  <figcaption>This is the URL that is being typed in within the GIF below.</figcaption>
</figure>
<figure>
  <img src="{{ site.baseurl }}/img/normalize-compare.gif" class="image--full-width" alt="a gif showing how you add the tags to the url separated by an ellipsis (three periods)">
  <figcaption>GIF of using the URL to see a diff between two tags.</figcaption>
</figure>
