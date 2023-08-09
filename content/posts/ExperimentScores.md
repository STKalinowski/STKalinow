---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Experiment: Scores'
pubDate: 2023-07-05
description: 'Small experimentation with the ideas of software 2.0 by letting the model take care of everything.'
author: 'Stanislaw Kalinowski'
color: 'F1C550'
---
I create a simple web page to score sentences based on input traits.

The idea is to let the models to take care of all the hard stuff, while we are just left with connecting everything up.

In this case we are creating a page similar to my Lenses project, but now the model does the heavy lifting.

It will take in some input text, a set of traits, and the output would be scores for each sentence.

We pass these inputs to the model, and it does all the parsing and scoring in one go. Done.

It's far from a perfect implementation. I didn't even experiment that much with the prompt either.

We could improve our prompt, make it multi pass, do chain of thought, etc.

But this isn't the point of the experiment, its just to show the idea of this delegation idea.

There is the general language task of ranking the sentences, which language models let the computer do. But there is also the difficult task of parsing natural language. We don't fret over rules, the model just understands what is a sentence and isn't, from vibes!

So currently this crude implementation isn't cleanly working, but its shows this idea. I created this pretty quickly, slamming components together, a single query, done.

I still think anything consistent will require hard coded programs, but anything with a little wiggle room can build on this idea. 

Link to the repo: https://github.com/STKalinowski/Scores

I built it on replit because I wanted to see how that platform was doing, so here's the replit link.

Replit Link: [https://replit.com/@StasKalinowski/SimpleScores?v=1](https://replit.com/@StasKalinowski/SimpleScores?v=1)