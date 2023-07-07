---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Experiment: Encoder-Decoder Generation'
pubDate: 2023-07-07
description: 'Better encoder-decoder generation with one simple change'
author: 'Stanislaw Kalinowski'
color: '2BA5FF'
---
I was reading through this [CodeT5 paper](https://github.com/salesforce/CodeT5), and this plain sight idea struck me; for encoder-decoder models, why aren't we prompting with a separate decoder part? Like we have our input prompt to the encoder, but we could also add another part of the prompt to be used in the decoder.

It might be mentioned somewhere, but I couldn't find anything.

In prompting, we are trying to influence the output of the model. This influence is seen not only in the text we write, but the form we write it in. For encoder-decoder models, its just makes sense to keep the core of the ideas in the encoder input, and any meta-structure (ex. Summary:, ```JSON, "The key ideas of the text are ...", etc) should only go into the decoder part. 

So, make the encoded section represent the ideas and the task. 

While the decoder receives some starting template to influence the generation.

You wouldn't want to always do this. It works main for tasks which have a natural shape/starting point. So, for a outline generation task:
Encoder input is "Create an outline for the following story. {story_traits}"
Decoder input is "Outline:\n Beginning: "
Here we are giving the model a starting text to begin generating from! But it isn't muddying the encoding part!

[Here is a link to my notebook doing this with HuggingFace using t5-flan.](https://github.com/STKalinowski/EncoderDecoderModelBetterGen)

It's not a complete end-all be-all solution, but this would have been such a useful trick for me had I thought of it earlier.

Example results:

First keep in mind. These where generated using flan-t5-large, which is just a bit under 1B params! flan-t5 also isn't trained on code data as far as I know, which means strictness of formatting isn't as strong.

![WriteOutline.PNG](/Images/EncoderDecoder/WriteOutline.png)

We can see above how our starting prompt of "Outline:\n Beginning:" funnels the generation, giving a frame work.

![GenuineOutput.PNG](/Images/EncoderDecoder/GenuineOutput.png)

![GenuineOutput2.PNG](/Images/EncoderDecoder/GenuineOutput2.png)

![BadQA.PNG](/Images/EncoderDecoder/BadQA.png)

The above example shows both the training bias and how our decoder input can have a negative influence!

![QA.PNG](/Images/EncoderDecoder/QA.png)

![WritingInf.PNG](/Images/EncoderDecoder/WritingInf.png)

![WritingInf2.PNG](/Images/EncoderDecoder/WritingInf2.png)

![Bob1.PNG](/Images/EncoderDecoder/Bob1.png)

![Bob2.PNG](/Images/EncoderDecoder/Bob2.png)

So hopefully this gives some idea on the technique of adding input strictly to the decoder. Gives us an avenue to influence the generation, but we need to be carefully test them out. I also suspect it to be more useful for models tuned on code because of the logic and formatting of the medium can be utilized!