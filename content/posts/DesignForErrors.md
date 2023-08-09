---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Thoughts: Design for errors.'
pubDate: 2023-06-19
description: 'LLM applications should design around errors & corrections.'
author: 'Stanislaw Kalinowski'
color: 'A1C45A'
---
While working on my D&D application, I've been thinking about designing around language models. I've come to the conclusion that any application using language models should design around correcting them.

I was trying hard to make my “DM” as correct as possible. Wrangling the prompts, contexts, and pipelines, and I realized, we can't guarantee perfect information.

Communication is a hard thing we even struggle doing between people. Who hasn't misunderstood someone or needed clarification. Watching D&D play throughs confirmed this for me, there are plenty moments of clarification and correction. 

Language is just ambiguous, we make assumptions and stamens we think are concrete are actually vague without our internal context. Sure, we can improve our model & systems to automatically grab such context, but there is just a natural vagueness in language. I'm sure we've all had the phenomenon of a perfect image in our head, but putting it on paper just doesn't reflect our ideas.

> “The only writers who have any peace are the ones who don't write. And there are some like that. They wallow in a sea of possibilities. To express a thought, you first have to limit it, and that means kill it. Every word I speak robs me of a thousand others, and every line I write means giving up another.” - Stanislaw Lem, Hospital of the Transfiguration
> 

If we want to instil such strict level of specificity, we actually have a system for this, its called programming. But, the benefit of using language models is that they can work with language, they reduce the need for such a level of specificity.

Therefore, I think when designing applications around language mode, there will naturally be incorrect outputs, and the focus should be on making the process of correcting them seamless. The model will get something wrong, make it easy for the user to correct it.