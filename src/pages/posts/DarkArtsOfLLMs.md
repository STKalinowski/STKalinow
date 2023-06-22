---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Thoughts: Dark Arts of Language Models'
pubDate: 2023-06-20
description: 'Thoughts about the future of applications and augmenting them with LLMs.'
author: 'Stanislaw Kalinowski'
color: 'EA4C4C'
---
I've been tinkering with LLMs and they're cool because we can ask them stuff in plain english and they respond accordingly! But the real sorcery begins when we ask them to reason, and they can do this! We've got computers to "think", we've invented magic!

Now, I understand, it's not real magic, they aren't doing real reasoning. It's an imitation, through the use of statistics and the process of predicting the next word. But I don't think it matters.

I like to view their capabilities of the models like a movie set. While on set, we're in the Wild West! But, as we start walking to the edge, it's clearly not the main street, turns out, we're in a parking lot. For language models, they have a constructed movie set of their own where we can act & do scenes in. As long as we remain on set, our shots will appear believable. For language models, their movie set is constructed from their training data, and shooting scenes are the prompts we give the model. The closer we keep our prompt to the training data, the mode believable and on set we will be. So asking the model to give writing feedback will go great because the model has likely seen something of the sort. Asking a model to program in a new programming language it has never scene is going to perform poorly because it hasn't been trained to do this.

Luckily, the training data for these large language models is so immense and the parameter count so large, that we effectively get a reasoning engine. Effectively in the sense of, most reasonable things you can ask it to do are likely to fall somewhere in the training data.

Whether the language models have true reasoning or not, it does not matter. In the end, if the output is close enough, then we can put their abilities to work.

Now, when putting large language models to work, we can use them to do informational work for us, but the real dark arts lies in their use as reasoning engines. What we can do is connect programs together with LLMs. The models will act as reasoning engines, where they receive input, are prompted to reason and "think" about the input, and then make decisions appropriately. We can use them as a connective tissue. This idea is in the vein off [Software 2.0](https://youtu.be/y57wwucbXR8), where we let the model and the data design the behavior. Where we worry less about the complexity and variety of situations, because we rely on the model to make reasonable decisions based on the input.


We can apply the idea to act between programs, processing and formatting the inputs and outputs. Or we can take steps to make it handle more and more tasks, having it think about the order of operations and which functions to call. On the extreme end is having the model act as the sole entity of the program itself, one of the earlier interesting experiments of GPT3 was having it pretend to be a backend server. This is a bit extreme, and the better applications are in domains with high variance or variability, so think things like level generation, creating suggestions for users, or working with user input.

User input is the application of LLMs which fascinates me the most because it lets us relax the interfaces we need. Computers always require such structured formatting with their input forms and structure, but by using language models, we can relax these requirements.

[There was this great article discussing chat bots and interfaces](https://wattenberger.com/thoughts/boo-chatbots), I would recommend. It highlights the benefits of chat bots, with them giving an pure open text-box, users are allowed to structure their input in the way they want. This allows them to use these chat bots dynamically, one moment asking for ideas with the next asking for feedback. But the article highlights the problem with this freedom, blank text-boxes don't give any structure, they don't tell the user how to use them, and they require constant work of typing out the context.

But here is where we can apply the dark arts, language models can solve their own problems! They be used to provide structure for the user, by giving suggestion prompts or generating interfaces, like buttons & sliders, dynamically. This can be done because we can feed the context where the language model can reason about the current desires of the user. We can reduce the work of the user by creating systems which automatically feed the model the context, where the application reaches a level of point and understand.

[GitHub Copilot](https://github.blog/2023-05-17-how-github-copilot-is-getting-better-at-understanding-your-code/#:~:text=How%20GitHub%20Copilot%20understands%20your,any%20point%20in%20your%20coding.) is an example of automatically providing context. It's a code generation application which automatically looks at surrounding text and accompanying files when generating code suggestions. The user doesn't have the burden of inputing all the relevant parts of their code.

[Wordcraft](https://wordcraft-writers-workshop.appspot.com/learn) is an example of prompt suggestion. They ran a study with a set of writers and their demo writing app Wordcraft. The application doesn't just generate text with language models, but it also creates suggestion prompts based on what is currently written. These auto generated prompts match the situation and can help give structure plus reduce work.  

Where I see programs headed, they are going to augmented with these language models, creating dynamic programs. Where we can use them for interfaces like I've discussed or for even between programs. The models can reason about what to query. the format, or reason about results of functions. We can break from the rigidity of hard coded programs and insert the reasoning engines to create flexible ones. 

Lets pause and discuss note-taking. Given a piece of paper, everyone has their own system of notes, and it changes depending on the task. At one moment we could be writing a web of ideas, drawing diagrams and pictures. In the next we could be diligently noting down everything the lecturer is say, starting the bits we don't understand. Notes & paper are dynamic, they fit into our form of thinking. 

I see a form of programs where the interfaces are dynamic, where the programs are dynamic, where the software adapts to the our mode of thinking and needs, mirroring the fluidity of pen and paper. Just as our note-taking shifts to accommodate varying tasks, we could have our software morph and modify in real-time to better fit our needs. I imagine a future where software is not a rigid predefined tool, but a flexible partner in our process.

LLMs can help enable these fluid programs, through thinking and adapting about our situation and desires. The future of software could consist of two thing, a model and a database, and everything else is generated.

Currently, these fluid systems aren't completely practical. The models aren't THAT smart. Inference takes too long. Compute power, especially on the edge, is limited. But we are in those early days of technology, and we don't know the limits & feasibilities yet. The glimpses are there, the road ahead looks promising, there is plenty of room, let's be positive and keep moving.