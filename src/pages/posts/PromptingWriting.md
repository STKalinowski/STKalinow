---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Thoughts: Is prompting just writing?'
pubDate: 2023-06-15
description: 'Connecting the idea of abstract pyramid to prompting LLMs.'
author: 'Stanislaw Kalinowski'
color: '16AA98'
---
Learning how to write, I was watching Brandon Sanderson's Lectures, and I cam across the idea which encapsulates the idea of prompting, the pyramid of abstraction.

[Mentioned in lecture 8 on world building](https://youtu.be/W1afbpM80b0), the pyramid of abstraction is about ambiguity and the number of interpretations a reader can have for a piece of writing. Anytime anything is mentioned, there are a range of interpretations it can naturally have.

Write “A door.” and there are a wide variety of doors people can imagine. Big doors, old doors, red doors, blue doors, etc. The writing is abstract and ambiguous, the distribution of interpretations is high.

But if we write “An old brown door”, then the ranges begin to collapse. By adding descriptions, we narrow down the possible interpretations people can have.

Context also helps, “For the old cabin deep in the forest, they stood in front of the door.” 

Granted, adding context makes it a longer sentence, but it reduces the amount of work overall. We no longer have to spend time describing each detail, the readers can infer most things from the context. With the assumptions, we focus on the important stuff, like a key plot element: “An axe slanted beside the door”, or pointing out anything unusual: “Rays of gold and purple shone out from the door windows”. 

Interpretation of these contexts does rely on the reader having background familiarity. So most people know have a sense of what a modern day cabin in the woods looks like, but this range widens with unfamiliarity, like a cabin in the woods in 1665, Sweden. We as readers have some understanding, but it's less common knowledge and therefore has higher variance. This is to say that context depends on the readers background knowledge and we make modern day assumptions about our readers. And is also why in my communications class we spent so much time discussing the background of the texts, writers make assumptions about their readers.

Hearing this concept, my mind immediately linked it to prompting. Prompting is just giving input to language models. Over simplified, language models are just predicting words based on the words which came before them, we get them to do work for us by structuring our prompts. This crafting of prompts is the abstract pyramid, we are trying to reduce the range of interpretations. We use similar ideas of defining the context and instructions to corral the models outputs, the interpretations. There is a meta factor to this, because we aren't just worried about interpretation, but about the output generation, which brings the additional concern of physical format.

But be warned, there is a difference between language modal interpretation and people. Language models have their own “language”. They work with text and imitate our natural language, but applying the pyramid of abstraction from normal writing to prompting is not 1 to 1! You can't just think of how a person would interpret the text and apply it to prompting, language models have their own interpretations, which we must learn. 

The underlying data the models where trained on make a huge difference, especially if it's an instruction tuned model.

Base models are interpreting inputs in a more literal fashion, so imagine all forms of writing like webforms, comments, documents, etc. And imagine what could come next. There is a meta structuring involved, you can't just tell the model to generate something, you need to make the format believable! 

Instruction models are different, where they are biased towards instruction. They automatically lean towards an instruction interpretation, and so telling the model straight up works better. However, it is important to stick closer towards the formats of instructions the model was tuned on. I know my usage of t5-flan improved when I learned the underlying templates used.

Instilling interpretation is important for models, we are trying to make the outputs clear, because the task of predicting the next token/word is inherently not well defined.

[There was this talk given at GDC about an animation generation model and is a clear example of the unwell defined problem.](https://youtu.be/o-QLSjSSyVk) Their model, not a language model, generates the character animations dynamically. One issue they ran into was going from stopped to running, the model didn't know which leg to start the animation with, left or right, either is okay, one just needs to be chosen. This issue caused the probabilities to be meshed together, causing a weird floating effect. Their solution was to have the model bias different legs depending on time, clearing up the undefined part. Language models suffer a similar problem where their word choices are undefined, there are many potential words which work just fine and approaches we can use. Prompting helps define the situation for the model, producing better generations!

This problem defining is explains for many tricks seen in prompting, from few-shot examples working well, giving a clear structure, or prompts like “You are a successful writer”. We are clearing up the interpretation of the text, it's less confused about what the text and the next set of tokens could be.

However, the underlying data and training is important. Instruction models are fine-tuned with instruction data sets which make their interpretations more biased. Techniques like “you are a successful writer” become less potent. Especially when factoring in RLHF, means prompting instruction models becomes more about giving clear directions. 

So when working with based models, setup the situation, pay careful attention to the physical structure of the input, when working with instruction tuned models, focus on clear instructions.

And that's my view on prompting. We are just focusing on the interpretation pyramid of the model, where we wrangle them to specific desired ranges. This requires learning how the models interpret. Knowing the underlying training data helps with this understanding, but the only way to learn how a model interprets is by using the model yourself, they each have their own learning curve!