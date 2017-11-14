---
layout: post
title:  Creating a Maintenance Site with Express and Pug
permalink: maintenance-site-with-express-and-pug
date: 2016-09-09 23:50:00
description: Setting up a maintenance site for multi-domain routing.
keywords: express, pug, expressjs, site, server
social_title: Creating a Maintenance Site with Express and Pug
social_description: A simple way to set up multiple domain routing to separate maintenance/outage pages using Express and Pug (formerly Jade).
category: development
---

If you've ever had to create a maintenance page for your website when you need to do some server work or some larger database operation that will need your system offline, you've probably suffered a headache about how to do it well. How about if you have multiple sites that you have to take down and you want there to be a "we are down right now" but branded for each domain? This was the dilemma that I had to solve and I must say, I like what I came up with.

My first pass was to use a virtual host but it was a bit messy and caused for a lot of very WET coding. It also didn't have a good catch-all method. I decided on a very simple Express server paired with Pug (formerly Jade) and then went with AWS for the cloud service (I'll discuss AWS in a future post).

Here's an example repository to see this in action: [github.com/peterramsing/Maintenance-Site](https://github.com/peterramsing/Maintenance-Site)

## Here's what I did:

I made this for the company I work at, NaturalPoint, so I'm going to use their site as an example. As we have several web properties at NaturalPoint it's really the perfect proof of concept. It's super cool that we get to work with these new ways of doing things and set up servers on AWS. Gosh this project was fun!

## The Express app:

First off, I created a new project and initialized npm

* `$ mkdir maintenance-site`
* `$ cd maintenance-site`
* `$ npm init`
* We'll be using Express and Pug, so let's install those now.
* `$ npm install --save express pug`
* Let's get coding by creating the index.js file.
* `$ touch index.js`

{% highlight javascript %}
var express = require('express')
var app = express();
{% endhighlight %}

This is pretty standard for Express. We're going to have a file structure that consists of a `public` directory where we keep styles, images, etc and then our `views` directory which is the standard for the Pug template files. For the rendered Pug template to access the directories we'll need to tell Express what to return when the styles, and images are asked for.

```
|-public
  |-images
  |-styles
|-views
|index.js
|package.json
```

[app.use() Docs](https://expressjs.com/en/4x/api.html#app.use)

{% highlight javascript %}
app.use('/images', express.static('public/images'));
app.use('/styles', express.static('public/styles'));
{% endhighlight %}

## Next we need to set the view engine to Pug.

[app.set() Docs](https://expressjs.com/en/4x/api.html#app.set)

{% highlight javascript %}
app.set('view engine', 'pug');
{% endhighlight %}

After that we need to set up our Pug template. For the sake of simplicity I'm going to streamline this a lot but you'll get the point

[Pug Docs](https://pugjs.org/api/getting-started.html)

{% highlight html %}
html(lang="en")
  head
    meta(name='viewport', content='width=device-width initial-scale=1')
    title= siteName
    link(type='text/css', rel='stylesheet', href='styles/main.css')
    link(rel='icon', type='image/png', href='image/' + site + '.png')
  body(class=site)
    div.page-wrap
      header
        h1 #{siteName} is down. :(
        p We will be back up soon.
{% endhighlight %}

## The routing logic based on what the requesting domain

Alright, that's done. We now have two variables to use within the template. `site` and `siteName`. I find it's nice to have both because in our case I don't want "NaturalPoint" to be a classname instead of "naturalpoint". Or in the case of "Gears Sports" where there is a space. Now how to use them?

We're going to use `app.get()` and use a wildcard to get all requests. We'll then get the hostname and set the variables to use within the Pug template based on what the hostname is. This way we can brand the Pug template differently based on the different urls.

[app.get() Docs](https://expressjs.com/en/4x/api.html#app.get.method)

{% highlight javascript %}
app.get('*', function (req, res) {
    if (
        req.hostname === 'optitrack.com' ||
        req.hostname === 'www.optitrack.com'
    ) {
        // Is it OptiTrack?
        res.render('index', { site: 'optitrack', siteName: 'OptiTrack'});
    } else if (
        // What about Gears?
        req.hostname === 'gearssports.com' ||
        req.hostname === 'www.gearssports.com' ||
        req.hostname === 'gearsgolf.com' ||
        req.hostname === 'www.gearsgolf.com'
    ) {
        res.render('index', { site: 'gearssports', siteName: 'Gears Sports'});
    } else {
        // Everything else should render NaturalPoint
        res.render('index', { site: 'naturalpoint', siteName: 'NaturalPoint'});
    }
});
{% endhighlight %}

And there you have it. The magic is done to detect OptiTrack and Gears sites and then use NaturalPoint to catch all other domains. You can configure this however you'd like it but this made the most sense for us as NaturalPoint is our main site.

Then it's just the listening port and we're aces.

{% highlight javascript %}
var port = 80;
app.listen(port);
{% endhighlight %}

## Running it

I made my "start script" in `package.json` "sudo node index.js". This way I can run this quite simply with `npm start`.

## Testing this locally

I update my hosts file to accommodate this. You can update your hosts file at ` /etc`. I then add in the urls that I need to test.

1. `$ cd /etc/`
2. `$ sudo nano hosts`
3. Paste the example below where you feel it makes sense.
4. Save and close
    1. `control` + `x`
    2. `y`

```
127.0.0.1      www.optitrack.com
127.0.0.1      www.naturalpoint.com
127.0.0.1      www.gearssports.com
127.0.0.1      www.gearsgolf.com
127.0.0.1      optitrack.com
127.0.0.1      naturalpoint.com
127.0.0.1      gearssports.com
127.0.0.1      gearsgolf.com
```


## Putting it in production

This post is getting rather long so I'm going to do another post about how to put this in production soon. It's rather easy to get this going on AWS, where I set it up, and there are various other options. I'll explore those in that post.

I'll also explain how to point your urls to this so that you can completely take down your entire stack if you're replacing a switch or something like that.

I hope you found this useful. If you have any questions or found something not working quite right feel free to reach out to me on Twitter. [@peterramsing](https://twitter.com/peterramsing)
