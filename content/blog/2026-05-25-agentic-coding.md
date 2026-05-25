---
title: 'Thoughts on Agentic Coding (May 2026)'
date: 2026-05-25
tags: []
draft: false
slug: 'agentic-coding-may-2026'
---

I've thought for a while already to write down some of my thoughts on LLMs in general and agentic coding specifically.
Not because I think I have anything to add to a discussion that seems to currently consume everything:
It's rare these days to read anything where AI isn't mentioned at least tangentially. I'm writing it down because it might ultimately help me to collect my own thoughts,
reflect on them and then in a few years have a good laugh about how wrong I was.

## No more searches

Let's start with the good: AI largely replaced search for my coding-related questions. I can't exactly pinpoint _when_ the switch happened for me but at a certain point (by now quite a while back),
egregious hallucinations were rare enough that they mostly replaced my search engine usage.

Instead of searching, I just interact with a chat that typically gives me back a sufficiently decent response immediately.
This is a huge improvement - not just because it's much faster but also because it saves me from wading through gargantuan amounts of noise:
Badly written documentations, blogs that contain huge amounts of fluff just to bump those SEO-numbers (remember SEO?),
spammy sites that just regurgitated crawled content; I'm definitely not going to miss any of that.

## Harnesses starting to become good

A more recent development is that the harnesses used in Agentic Tooling were becoming good enough that the tools became usable on large code bases.
So far, the quality of LLM-output was largely inversely correlated to the size of the code-base: The bigger the code-base, the worse the output.

Nowadays, they're starting to get scary good at analyzing large quantities of code:
What are edge-cases that were missed? Suggestions on how to extend it for additional functionality? Where could a complex bug stem from?
For many questions of these sorts, they're starting to yield incredibly useful output in much faster time than I ever could.

Where I currently feel they are still lacking is architecture: What abstractions should we use? How to organize a code-base?
What trade-offs do we need to consider, and how do we decide on them? What do we enforce, what do we leave up to the individual contributor's choice?
These are questions where I still feel that we as humans have an edge - admittedly, I'm probably a bit biased because these are the questions I love to deal with.
But given all the progress so far, I suspect that it's just a matter of time until the models and harnesses get good enough to at the very least surpass me as well.

## The rise of the slop

Now to the bad.

I miss the days where looking at a piece of text, code, or any artifact of any kind usually revealed very quickly how much time someone spent in creating it.
And at least to some extent, how much of _my_ time it's worth spending with it, especially in a work-context.

Someone took the time to create an elaborate document explaining in great detail some piece of functionality and asking me to have a look at it? I probably should.
Someone making a large pull request for a code-base I'm responsible for, asking me to review it? They took the time to create it, so I can take the time to review it, fair game.
Someone writing a large email or message to me? Again: At the very least it took them some time to write it,
so unless I need to aggressively prioritize my time the least I can do is read it and answer appropriately.

These contracts have been broken. Nowadays, I frequently look at paragraphs of text, and I have no clue without reading it whether it's actually worth the time or not.
It looks good on the surface: The language is sophisticated, the document is well-formatted, but is it a genuinely useful document or is it just LLM-output based on a three-line prompt
that wasn't worth the token-usage to begin with?

In the past, I got excited when someone opened a huge refactoring pull-request. Not necessarily because I was looking forward to reviewing it or having the hard discussions of
whether or not we should go forward with it in what way, but because someone took the time and effort to address a pain-point they were having. Someone was motivated, fantastic!
Some of the best learnings I've had in my career were based on someone (in some cases myself) trying to address something they felt was worth spending time on.

Nowadays, I absolutely dread large pull requests. How much of it is genuine effort, and how much of it is just tokens burned mindlessly? Unless there are really obvious tells
(and as the harnesses get better, they are fewer and fewer), it's hard to distinguish between the two. And I don't mind per se to review someone else's AI-generated code:
It can still be good. It can still be useful. But if someone spends X amount of time to create code and I have to spend Y amount of time to review it,
this balance only works out if X is much bigger than Y.

Some could say: Just use an LLM to review or summarize it! Apart from the absurdity of it all, that only gets you so far: The bucket ultimately has to stop somewhere.
Someone _has_ to be accountable, and the only sure thing about this problem is that it won't be the LLM.

## Impact on Learning

Personally, I'm very happy that I have my formative years behind me. If LLMs existed during my years of studies,
I'm fairly confident I would have used them to a larger extent than what's pedagogically useful.

I can see it in today's junior developers and apprentices: The choice between trying to understand what an AI-Agent produces and whether it's good or not
versus just accepting its output and calling it a day is a tempting one. And even if one does not succumb to one's laziness, there are still challenges:
The learning-effect of "reviewing" is, at least in my book, definitely not as strong as "trying oneself". I can very well imagine a future where tomorrow's developers
will have a hard time getting anything done without AI-assistance of some form.

Another aspect is the problem that LLMs do not mind at all to generate more and more code to address a given problem.
One of the big benefits of having to do the "hard work" oneself is that one spends a considerable amount of time trying to hit the right abstractions:
If one can hit the sweet spot and get the abstractions _just_ right, that saves a lot of time down the road (and feels absolutely incredible).
Now that we have a tool to just generate code, why think about it much? Let's just generate some more!
Having the experience of getting abstractions wrong and living with the pain of having to write/debug/extend code in cumbersome fashion is not something the LLMs can have;
as writing code is no pain for them. As a matter of fact, the market-incentives are orthogonally aligned:
The more code generation that is needed, the less it becomes manageable by humans, which leads to more need for LLMs.

## Final thoughts

I tend to be a rather optimistic person who believes that ultimately in the long run, things tend to turn to the better.
AI in its current stage is an incredibly exciting and powerful tool, but to me also occasionally a cause of annoyance because it's not always
used with the necessary due diligence.

I've recently read a [comment on HN](https://news.ycombinator.com/item?id=48154451) that resonated quite well with me:

> \[..\] it’s quite a different experience going all Jackson Pollock with AI in your own studio on your own terms, compared to the sorry state of affairs of having 100s of Pollocks throwing paint around wildly within a corp to meet a paint quota.

Where exactly we're heading, let's see. Currently, it feels like it's a very useful tool but not useful enough to justify all the hype and push we're currently seeing.
To draw a parallel, it sounds a bit like the internet in the 90s before the dot-com-bust: Obviously the future but not necessarily in the timeline we currently think.

To finish out with a positive note, I'm largely convinced that long-term, AI will be incredibly transformative;
not just on how work is done but also from a societal point of view, of how work is valued and how we interpret the need for work.
There, I'm very optimistic. But that's a topic for another blog post.
