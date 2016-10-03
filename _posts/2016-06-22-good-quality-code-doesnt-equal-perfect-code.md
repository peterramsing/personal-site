---
layout: post
title:  Good Quality Code != Perfect Code
permalink: good-quality-code-perfect-code
social_title: Good Quality Code != Perfect Code
date: 2016-06-22 17:00:00
description: Great code, unless shipped, doesn't do much.
social_description: It's not just about writing delicious code. It's about writing code that's in production.
keywords: Web, Developer, Quality
audio: good-quality-code-doesnt-equal-perfect-code
category: development

---

We've all been there. You've written a pretty solid feature and you're just about done but you keep finding little areas to improve. Those little things that you keep committing such as "cleans up x" or "refactors x to make simpler". As your deadline approaches your stress level grows, the product owner is getting nervous, and the late nights are inevitable.

## Developers Versus Product Owner Priorities

| Developer           | Product Owner                               |
|:--------------------|:--------------------------------------------|
| Maintainable        | It Works                                    |
| TDD                 | Can add features when business needs change |
| Fully Documented    | Is in production creating value             |
| Clean Code          |                                             |
| Uses Best Practices |                                             |
| Etc.                |                                             |


So how do we deal with these two differing sets of priorities? I think the first step is to identify that **they don't differ in principle**. Many developers (like myself...I've got to throw myself under the bus here) will say *"The only way to give them what they want is for me to do this right!"*. I think the reverse could be said, though. Developers are hired to return value to their organization. They use code to bring this value, but **the code is not the product**. The result of the code is the value.

> Even great code returns no value for the organization until it is deployed into production.

Now let's not kid ourselves. If there is a bug in the code, fix it. If the code is written poorly, update it. If you're not proud of it, make it worthy of your talent. But stop seeking to perfect your code before shipping it to production.

Perfect code is only perfect till you look at it again. Just as you wouldn't nit-pick another developer's pull request with minor changes, the same applies to reviewing of your own code.

## Delivering Value To The Organization

Code is written to be shipped. Unless you're working on a spike, a proof of concept or some other caveat, let's keep ourselves on the same page and agree that we're talking about code that is associated with a ticket that is being written for a feature, enhancement, etc. The instant that your code is deployed to production you have earned your keep. Every minute that you spend nit-picking your code, refactoring this and changing that are minutes that you could be smoke testing, writing meaningful tests to harden your code or simply be moving onto the next ticket.

## Actionable Takeaways

So what do you do with this?

**Be really proud of what your code does.** What your code does is just as, if not more, important than *how* your code does it. Be proud of the feature you shipped and don't simply seek satisfaction from the code.

**Don't shame product owners for wanting your code in production.** Saying "you don't understand why this is taking so long" is not an option. If they don't understand, it is for you to help them understand.

**Understand the business wants good code written just as much as you do.** I've never heard a product owner ask me to write worse code. Don't be silly! Just because they question to need to write tests or clean code up doesn't mean they're asking you to ship bad code. They're just wanting code shipped.

**Don't forget about maintainability.** As I'm encouraging you to stop striving for perfect code, I don't mean to implying you should write anything but your best. Also, do be aware of your code becoming debt. I highly recommend this [read from RJ's blog](https://rjzaworski.com/2016/06/technical-debt) about technical debt.
