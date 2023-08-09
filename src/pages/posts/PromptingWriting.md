---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Thoughts: Is prompting just writing?'
pubDate: 2023-06-15
description: 'Connecting the idea of abstract pyramid to prompting LLMs.'
author: 'Stanislaw Kalinowski'
color: '16AA98'
---
While learning how to write watching Brandon Snaderson's Lectures, I came across the idea of the "abstract pyramid". I believe it encapsulates the whole idea of prompting,(Prompting in the sense of language models.)

[Mentioned in lecture 8 on world building](https://youtu.be/W1afbpM80b0), the pyramid of abstraction is about the ambiguity of a piece of writing. It's focus is on the variety of interpretations a reader can have. Anytime we write something the piece of writing has a natural range of interpretations, not all readers see the exact same thing.

If we write just “A door.” and there are a wide variety of doors people can imagine. Big doors, old doors, red doors, blue doors. This piece of writing is abstract and the number of interpretations is high. But if we write “An old brown door”, then the ranges begin to collapse. By adding descriptions, we narrow down the possible interpretations people will naturally have.

Context helps, “For the old cabin deep in the forest, they stood in front of the door.”, the readers can infer the look of the door based of everything. Context is important because it helps reduce work and focus on the important bits of communication. By saying a old cabin in the woods, a image of a wooden worn down cabin appears. We now just need to spend effort detailing anything necessary, key plot elements: "An axe slanted beside the door", anything out of distribution: "Rays of gold and purple shone out from the door windows".

(Rewrite)
The non-normal portion was the point of Brandon's lecture, it's where we have opportunity to leave in world building. But this aspect highlights the fact that writers rely on the context of their audience. Most people have a sense of what a modern day old cabin in the woods looks like, the range is narrow. But asked to imagine a house in 1660 Sweden will be less familiar, and a wider range(maybe narrower, where readers converge to common stereo types). And this is why in my communications class we spent so much time discussing the backgrounds of text, especially for older ones. Writers make assumptions about their readers and their interpretations.

Therefore the abstract pyramid is about the range of interpretations, with both a focus on the words used and the background of the reader. The goal of the writer isn't to never to have one interpretation, [it's impossible](https://www.scientificamerican.com/article/people-differ-widely-in-their-understanding-of-even-a-simple-concept-such-as-the-word-penguin1/), but narrow the interpretation to a good enough range.

Upon hearing the concept, the link to prompting language models was apparent. Prompting is about narrowing the interpretation, involving both the words used and the background information. People have a background context of what they know, the equivalent in models is their training data. Our goal with prompting is the same as with writing, narrow the range of interpretations into the desired area.

Prompting models is different than writing for people. Not only is their understanding of the world different, there is a meta structural factor to prompting. The physical layout/structure plays a role in the interpretation.

To demonstrate how model interpretations work, lets take the pyramid of abstraction to its extreme. If we prompt a model, and give it as much details as possible, leaving no room for missinterpretation, are we going to find a perfect response? No.

The problem here is that the models interpretation is grounded in its training data. Think about the intructions we usually receive, they aren't as long and strict, most are contain a heavy amount of implications. (There is a domain which does contain less ambiguity, programming!).

Data plays an important part for interpretation, so think about your models training and fine-tuning data. If you're working with a base mode, structure plays an important role, leave hints in the formatting of your prompt. If you're working with a instruction tuned model, then it's biased to interpreting the input as instructions. If you're creating a finetune dataset, think about it in reverse, how should the model be interpreting input.

I've found this abstraction pyramid to be a valuable tool in crafting prompts. It's something I was doing already, just hadn't conceptualized and put a name to it till now.