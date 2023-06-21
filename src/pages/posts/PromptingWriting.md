---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Thoughts: Is prompting just writing?'
pubDate: 2023-06-15
description: 'Connecting the idea of abstract pyramid to prompting LLMs.'
author: 'Stanislaw Kalinowski'
color: '16AA98'
---
Learning how to write, I was watching Brandon Sanderson's Lectures, and I came across the idea which encapsulates the idea of prompting, "the pyramid of abstraction".

[Mentioned in lecture 8 on world building](https://youtu.be/W1afbpM80b0), the pyramid of abstraction is about the ambiguity of a piece of writing and the variety of interpretations a reader can have. Anytime we write something, there is a natural range of interpretations. 

If we write “A door.” and there are a wide variety of doors people can imagine. Big doors, old doors, red doors, blue doors. This piece of writing is abstract and the number of interpretations is high.

But if we write “An old brown door”, then the ranges begin to collapse. By adding descriptions, we narrow down the possible interpretations people will naturally have.

Context also helps, “For the old cabin deep in the forest, they stood in front of the door.” The readers can infer the look of the door from the context.

Now, granted, will take more words and create a longer sentence, but establishing context reduces work overall. We no longer have to spend time describing each and every detail. The reader will make assumptions from the context, and we can focus on specifying the important stuff like any key plot elements: “An axe slanted beside the door”, or pointing out anything unusual: “Rays of gold and purple shone out from the door windows”. 

Interpretation of these contexts does rely on the reader having background familiarity. So most people have a sense of what a modern day cabin in the woods looks like. But a cabin in the woods in 1665 Sweden is going to have a higher variability because modern readers are just less familiar with it. This is to day, context depends on the background knowledge the readers bring. And this is also why in my communications class we spent so much time discussing the backgrounds of the texts, especially for older ones, writers make assumptions about their readers.

Hearing this concept, my mind immediately linked it to prompting. Prompting is just the input being given to the language models. This is an over simplified,but language models are just predicting words based on the words which came before them, we get them to do work for us by structuring our prompts to make the predicted words the desired ones. The act of crafting our prompts is the act of narrowing down the abstraction pyramid. We are trying to reduce the range of interpretations into the area to make it useful. We use similar ideas of establishing specifics and context to shape the interpretation of the model into our desired ranges. There is a meta structural factor to prompting, in two senses. The models pays attention to the physical structure of our prompt, especially base models. And we also worry about the interpretation of the output, how will the model structure their output.

But be warned! There is a difference between language model interpretation and people. We cannot just think how someone would interpret the text! Language models have their own "language", they work with text and imitate our natural language, but its not exactly 1 to 1!  

The underlying data the models plays an important part in understanding the model and its interpretation, especially if the model is instruction tuned or finetuned. 

Base models are interpreting inputs in a more literal fashion, this is where a more literal imagining of "what text could possibily come next" is useful. This means that the meta structuring is more important, you can't just tell the model to generate an answer, you need to format it so the answer will appear in the prompts continuation.

[Example here?]

Instruction models & fine-tuned ones are different, they are biased towards an interpretation. Instruction models in particular lean towards an instructional interpretation, so the focus should be more on tell the model what to do. However, it is important to stick closer towards the formats of instructions the model was tuned on. I know my usage of t5-flan improved when I learned the underlying templates used.

Instilling interpretation is important for getting performance out of models, we are trying to make the output as clear as possible because the task of predicting the next token/word is inherently not well defined. The task sufferers from the unwell defined problem. This being that there are many potential correct answers to generate, not just in the range of words to use, but the order teh words can have.

[There was this talk given at GDC about an animation generation model and is a clear example of the unwell defined problem.](https://youtu.be/o-QLSjSSyVk) Their model, not a language model, generates the character animations dynamically. One issue they ran into was going from stopped to running, the model didn't know which leg to start the animation with, left or right, either is okay, one just needs to be chosen. This issue caused the probabilities to be meshed together, causing a weird floating effect. Their solution was to have the model bias different legs depending on time, clearing up the undefined part. Language models suffer a similar problem where their word choices are undefined, there are many correct generations it can make, with the choice of words, the choice of order, and the choice of situation. Prompting helps define and make the answer more concrete, producing better generations!

This concreteness establishing can explain many tricks seen in prompting, from few-shot examples working well, giving a clear structure, or prompts like “You are a successful writer”. We are making a clear interpretation of the text, it's less confused about what the next token could be.

However, the underlying data and training is important! Instruction models are fine-tuned with instruction data sets bias the models, it's essentially establishing a default interpretation. Techniques like “you are a successful writer” become less potent. Especially when factoring in RLHF, prompting instruction models becomes more about giving clear directions, because the situation is partially established.

So when working with based models, setup the situation, pay careful attention to the physical structure of the input.  When working with instruction tuned models, focus on clear instructions. Keep in mind the underlying training data. 

And that's my view on prompting. We are just focusing on the interpretation pyramid of the model, where we wrangle them to specific desired ranges. This requires learning how the models interpret, factoring in the training data, and getting a feel for the model through usage.