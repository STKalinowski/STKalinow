---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Project: Fiszka'
pubDate: 2023-07-31
description: 'Setting out to solve spaced repetition.'
author: 'Stanislaw Kalinowski'
color: 'EA4C4C'
---
I am a fan of spaced repetition. 

Plenty of articles have been written advocating it, here is my favorite, [Augmenting Long-term Memory by Michael Nielsen](http://augmentingcognition.com/ltm.html)

The technique is not only let's you choose what to remember, but demonstrates the power of computers. The storage, organization, and scheduling is all handled by these spaced repetition programs. Your only task is to create, pick and choose what goes in.

Past the benefits, spaced-repetition and flash-carding isn't perfect. The cards created matter. The question of transferring outside the program matters. And the effort + habit needed for the practice.

[I enjoyed this discussion on the adoption of the practice](https://michaelnotebook.com/mmsw/index.html), and why isn't everyone using it. With it's analogy to surfers, it brings up two facets for the practice. There is the technological side, the tools being used. There is the cultural side, the mental habits and concepts in wide spread use. 

Fiszka is my technical solution. Experimenting with LLMs, its clear to me and many that this technology could be used to solve some of the problems with the practice of space repetition.


### Problem 1 - Card creation.

One of the most natural notions of applying LLMs to the space is the generation of cards. 

Card generation is both difficult and effortful. There is a skill to creating cards, which has to be learned and improved through practice. It's a effortful thing. This effort isn't necessarily a bad thing, the process of creating cards is part of the learning. Thinking how to properly break down and atomize ideas into cards is a teaching process.

Therefore, although models can write cards, some are arguing against the practice of generating cards, some are extreme enough to call off using any cards but your own.

While I believe its true, that there are benefits to creating your own cards, and the effort of going through it is fruitful. 

Using pre-written cards is fine.

It becomes similar to how tests work. They still provide feedback of what you know and don't know. And are still guaranteed to be learned by being in the system.

Pre-written cards provide their benefit by saving effort & time, as well as in providing a base line quality to cards. Writing cards is a skillfull act. By training a model to write quality cards, beginners get to learn what quality cards look like and the practice becomes more accessible. 

The generated cards versus writing cards doesn't have to be a mutually exclusive thing, both can be done. Writing cards provides its benefit in the act of thinking and breaking down information into atomic concepts. If you are studying a new domain and just need to memorize the terms right now, get a model to write those cards. Heck, we can generate cards and then write the cards we feel needed added. 

Generated cards provide benefit of accessibility, saving time, and reducing rote work. 

### Problem 2 - Over fitting problem.

A problem any practitioner might have ran into, overfitting to cards. When we learn just the answer to cards, and fail to generalize and apply the idea in situations outside the flashcards. 

This is a major issue. What's the point in learning flash cards if we fail to remember them outside the program.

Now good high quality cards plays a part in addressing this. It's why modern advice to writing cards involves focusing on the 'why' of ideas. The cards need to try to build up a system and general understanding.

Another feature I'm adding to address this is card rewriting. Fiszka will take some subset of cards, a provide a temporary rewritten version. Where the version is questioning the same thing. With the card looking different, we need to learn a slightly more general understanding of the idea. 

This slight jiggling of the range required to know a topic, the card + the range of rewrites, in combination with quality cards should help with instilling a more general understanding of the ideas.

### Conclusion

There are a range of ideas and features I want to pursue. But, from my experience, it's better to start simple and let things grow. One day I will explore simulations, shared learning, and automatic coaching. But for now, I just plan on keeping it simple and focusing on addressing my main two problems with space repetition.
