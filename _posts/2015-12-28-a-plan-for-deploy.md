---
layout: post
title:  A Plan For Deploy
date:   2015-12-28 16:40:16
description: Deploying our new TrackIR Site.
---

Lately I've been thinking a lot about [decision fatigue](https://en.wikipedia.org/wiki/Decision_fatigue). So when this last week we got the thumbs up from the CEO and were ready to deploy our [new site](http://www.naturalpoint.com/trackir/), I wanted to make sure that the deploy went as smooth as possible and kept decision fatigue in mind.

Whenever one deploys to an older codebase there is a risk that something goes wrong. We have testing environments but our older code can sometimes find its way to cause issues that we can't spot on Staging or in Testing. When we started on the new site weeks before I began the planning process to ensure that the night of the deploy I was ready to think and make the decisions that I needed to make, not ones that could be thought of before the deploy.

The actual deploy consisted of very few steps to get the new code live. First, put the new code on the server and second add some aliases to the apache config. There were two goals in mind when doing this "simple" deploy.

1. Maintain uptime of all critical processes on all four web properties.
2. Be able to roll back at any point in the deploy ~~if~~ when something goes wrong.

We have four web properties touching the same backend code to manage their cart and checkout process. Luckily we weren't dealing with anything new in the database so that wasn't an added step.

Here's an abbreviated version of what my decision tree looked like:

* Build out NaturalPoint V2 Production Jenkins Item.
  * ssh into server and verify the files are in order and symlinks are in spec.
    * *if not*
      * verify that the site is still functioning and then review Jenkins cofig–go back to start.
    * *if yes*
      * proceed
* Deploy new Puppet config to production server
  * Test if new site is visible on [www.naturalpoint.com/trackir/](http://www.naturalpoint.com/trackir/)
    * *if not*
      * Is the site up at at all?
        * *if it's still on old site*
          * Review the apache configs on production via ssh and determine if they were adjusted. Work with Puppet script to resolve the issue.
        * *if the site is not available at all
          * *Immediately* roll the apache config change back with Puppet - verify site is back to old codebase. Review apache change and start over.
        * *if the site is up on new codebase*
          * Test to ensure server includes are working, store is working, checkout is operational, etc.
          * *if any tests fail* Immediately roll back apache change. Test again on old codebase and if it still doesn't work Build out NaturalPoint V1 Production Jenkins Item–this will revert all code back to previous state.
* etc, etc, etc...

Starting 22:30 last Monday I got on the phone with our remote IT chap who would be managing the apache configs as we have our production server managed by Puppet which is in the brilliant hands of some gents offsite. The night went a lot longer than expected and while there were a few tense moments there was never a question about the stability or availability of the critical services. Because of the thinking went into the planning I didn't need to worry about "should we roll back?" or "is this right?", it was already known.

So what if it took twelve times longer than if everything went off without a hitch? It's unavoidable when you're in dev/ops. Because there was a solid plan in place there wasn't much stress. When I finally crawled in bed early the next morning I wasn't trying to calm my brain. There was a plan, it was executed, and the decisions were made ahead of time not right in the thick.

TL;DR

When you have the decisions already made you leave your head clear to make the decisions that need to be made on the fly much more educated and well processed.
