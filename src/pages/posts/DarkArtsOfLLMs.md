---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Thoughts: Dark Arts of Language Models'
pubDate: 2023-06-20
description: 'Thinking about the future of programs and the use of LLMs to augment them.'
author: 'Stanislaw Kalinowski'
color: 'EA4C4C'
---
I've been tinkering and working with LLMs recently and they're extremely cool because we can just ask them stuff and they understand our language! But the coolest part about them is when we ask them to reason, and they can do this! We can get computers to think, we've invented magic.

Now, I understand, it's not real magic, they aren't doing real reasoning. It's just an imitation through the process of predicting the next word. But I don't think it matters.

I like to think of the models & their capabilities like a movie set. While on set, we're in the Wild West! But, as we start walking to the edge, it's clearly not the town square, turns out, we're in a parking lot. For language models, they have a constructed movie set, based on their data, and we can act & do scenes in the set, prompting. As long as our scene is on set, it will appear believable, and as long as our prompt is close to the models training data, it can give a reasonable answer. So, asking for model feedback, it's probably seen that before, asking for comments on  recent news, well it will give an appearance of a good answer, but the contents will be bad. Same goes for when asking it format answer, JSON will give better performance, a new format we invented is going to struggle more. The models movie set is based on its training data and its parameter size.

Luckily, the training data for these large language models is so immense and the parameter count so large, that we effectively get a reasoning engine. Effectively in the sense of, most reasonable things you can ask it are going to fall somewhere in the training data.

Whether the language models have true reasoning or not, it does not matter. In the end, the output is close enough and we can put their abilities to use.

Now, when putting large language models to use, we can use them to do informational work for us, but the real dark arts lies in their use as reasoning engines. What we can do is connect programs together with LLMs. The models receive input from one part of a program, they reason and “think” about the input, and then make decisions appropriately. We have them acting as connective tissue. This is the idea, or in the vein off, [Software 2.0](https://youtu.be/y57wwucbXR8), where we let the model and the data design the behaviour. 

The idea can be applied in any program. One of the early interesting experiments was having the language model act as the sole backend. But better applications for this idea are situations of high variability, so think things like level generation, creating suggestions for the user, or working with user input.

User input is the application which fascinates me the most because it relaxes the interfaces we need. Computers always require such structured formatting with their input forms, but language models can relax this.

There was this great article discussing chat bots and interfaces, I would recommend. It highlights the benefits of chat bots, with them giving an pure open text-box, users are allowed to structure their input in the way they want. This allows them to use these chat bots dynamically, one moment asking for ideas with the next asking for feedback. But the article highlights the problem with this freedom, blank text-boxes don't give any structure, they don't tell the user how to use them, and they require constant work of typing out the context.

But here is where we can apply the dark arts, language models can solve their own problems! They be used to provide structure for the user, by giving suggestion prompts or generating interfaces, like buttons & sliders, dynamically. This can be done because we can feed the context where the language model can reason about the current desires of the user. We can reduce the work of the user by creating systems which automatically feed the model the context, where the application reaches a level of point and understand.

[GitHub Copilot](https://github.blog/2023-05-17-how-github-copilot-is-getting-better-at-understanding-your-code/#:~:text=How%20GitHub%20Copilot%20understands%20your,any%20point%20in%20your%20coding.) is an example of automatically providing context. It's a code generation application which automatically looks at surrounding text and accompanying files when generating code suggestions. The user doesn't have the burden of inputing all the relevant parts of their code.

[Wordcraft](https://wordcraft-writers-workshop.appspot.com/learn) is an example of prompt suggestion. They ran a study with a set of writers and their demo writing app Wordcraft. The application doesn't just generate text with language models, but it also creates suggestion prompts based on what is currently written. These auto generated prompts match the situation and can help give structure plus reduce work.  

Where I see programs headed, they are going to augmented with these language models, creating dynamic programs. Where we can use them for interfaces like I've discussed or for even between programs. The models can reason about what to query. the format, or reason about results of functions. We can break from the rigidity of hard coded programs and insert the reasoning engines to create flexible ones. 

Lets pause for a second to discuss note taking. Given a piece of paper, everyone has their own system of notes, and it changes depending on the task. At one moment we could be writing a web of ideas, drawing diagrams and pictures. In the next we could be diligently noting down everything the lecturer is say, starting the bits we don't understand. Notes & paper are dynamic, they can fit into our form of thinking. 

I see a form of programs where the interfaces are dynamic, where the programs are dynamic, where the software adapts to the our mode of thinking and needs, mirroring the fluidity of pen and paper. Just as our note-taking shifts to accommodate varying tasks, we could have our software morph and modify in real-time to better fit our needs. I imagine a future where software is not a rigid predefined tool, but a flexible partner in our process.

The future of software could be two thing, a model and a database, and everything else is generated.

Currently, these fluid systems aren't completely practical. The models aren't THAT smart. Inference takes too long. Compute power, especially on the edge, is limited. But we are in those early days of technology, and we don't know the limits & feasibilities yet. The road ahead looks promising, there is plenty of room, let's be positive and keep moving.