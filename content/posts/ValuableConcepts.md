---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Thoughts: My most valuable concept.'
pubDate: 2023-08-08
description: 'Compression, Simplification, Generalization = Learning'
author: 'Stanislaw Kalinowski'
color: '16AA98'
---
I've played league for a while, and [one particular post on the league subreddit has resonated with me.](https://www.reddit.com/r/leagueoflegends/comments/jtysag/dopa_reveals_his_secrets_after_his_last_season/) This post was a translation for a discussion Dopa had on stream after reaching rank one.He discusses his idea of concepts, really just breaking down the game into a set of facts, whoever has the best facts wins. You don't own them, you can take other peoples concepts and refine them.

I think about this post from time to time. And I figured I'd share my most valuable concept: 

Compress and simplify your knowledge as much as possible.

Compression of knowledge plays a role in all of retrieval, generalization, and simplification. The most elegant solutions are simple.

The idea that compression is intelligence has been floating around, at least in the circle of ML.

[I read about generalization from this post.](https://pair.withgoogle.com/explorables/grokking/) It's looking at the grokking effect and generalization. Looking at models on a spectrum between memorizing the solution and generalizing the solution. 

Weight decay is a pressure on the model, making in generalize because with generalization the model learns to represent more with less.

Comparing such pressure to our own learning, by compressing we create more general understandings. With generalizations we can apply the knowledge to more diverse situations.

[This blog post discusses their link between compression and good research.](https://rs.io/developing-good-research-skills-compressing-knowledge/) Discussing all about how we are compressors. Interesting information upgrades our ability to compress?

I like this quote from John Baez “Keep synthesizing what you learn into terser, clearer formulations. The goal of learning is not to memorize vast amounts of data. You need to do serious data compression, and filter out the noise.”

Building Fiszka, my spaced repetition application, I'm thinking about how to reinforce the compression process. Flash carding doesn't emphasize this aspect of learning, and can even harm it, through over fitting and reliance on cues specific to the card.

My application already temporarily rewrites a subset of cards to combat this overfitting, but I need to figure out a way to encourage compression and generalization. 

Of my set of ideas, the simplest one might be best: Ask the user to compress and generalize. Give them a clustered set of cards and prompt them to write simplest explanation possible. Maybe place a limit on words, characters, etc.