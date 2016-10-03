---
layout: post
title: Define Your Assumptions
permalink: define-your-assumptions
social_title: Define Your Assumptions, what are the assumptions disguised as fact?
date: 2016-07-10 09:00:00
description: what are the assumptions disguised as fact?
social_description: It's easy to have assumptions hide in the facts. What facts have you held as fact that were in fact assumptions?
keywords: web development, development, project management, assumptions, legacy code
audio: define-your-assumptions
category: development

---

There are numerous moments when I have assumed something was fact when it was really just an assumption. Whether it was my own assumption or I was hearing an assumption of someone else it's not hard to see the trouble this could cause if we step back a moment.

We all assume things about services, people, apis, legacy code, you name it. Assumptions are great. There where creativity can really begin. *"What if we try this..."* is an assumption and can lead to great inspiration. What can take a harmless assumption and give it negative power is when it's considered fact.

## Assumptions in Meetings
How often have you been in a meeting where assumptions were tossed around like facts? It's rarely on purpose. Sometimes it's caused by pressure from product owners to make decisions quickly. Sometimes it's a bit of pride not wanting to admit we might not know something backwards-and-forwards. Other times it's simply ignorance to the damage our assumptions can make if not identified as assumptions.

## Assumptions Hiding in the Facts
I was working on a project and was told early on about a particular blocker in the legacy code. It was understood by all that to break the blocker would take months of development and be extremely expensive. This held up several features and caused for considerable angst when what seemed like obvious UX wins had to be sidelined because of this blocker.

One day another dev on the team asked me what assumptions about the blocker I was making were. He offered an idea that was from the perspective of the blocker being an assumption instead of fact. I spun around in my chair and coded up a proof-of-concept based on this new idea.

No joke, five minutes later that several month and costly blocker was broken. That prototype actually only took about two more minutes of polish and it's in production today. When the statements made about the blocker were isolated into facts and assumptions, creativity won.

## How to handle assumptions?
1. Don't be the cause of assumptions being considered facts.
  * If you don't know, just say so. If you are on a team that doesn't value that honesty then it might be time to move on.
  * Check yourself if you find you are often moving on quickly from problems considering them too hard. Ask yourself "what am I assuming here?"
2. Watch for assumptions of others.
  * If you hear "that should be hard and expensive" without anything to back it up. Ask a follow-up question. "Are there any assumptions here that we might be considering as fact here?"
  * Don't assume just because that's what everyone else says it is fact. This is a tough balance because institutional knowledge is extremely powerful but be wary of the institutional knowledge that's vague.
  * Always be respectful of others (and this is key). Even if their facts are assumptions, often there is good reason they hold them as fact. Don't just "assume" that they're foolish for thinking something is fact when in reality it is an assumption.
