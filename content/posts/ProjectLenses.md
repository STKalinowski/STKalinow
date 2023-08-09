---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Project: Lenses'
pubDate: 2023-06-30
description: 'Exploring the idea of viewing text as a map.'
author: 'Stanislaw Kalinowski'
color: '2BA5FF'
---
Computers can now understand our language, how can we apply this to processes. One of the ideas is viewing text as a map. Normal reading, Top to Bottom & Right to Left. Maps, visually display information which is immediately recognizable, zoom in and out.

This map like approach is what I'm going for in Lenses.

First the application begins by bringing in the text you're reading, you can paste it in or provide a link and it will try its best to get the relevant text.

Then once we have the text displayed there are two main features:

Lens Views & Map Summary.

![Screen Shot 2023-06-29 at 7.08.18 PM.png](/Images/ProjectLenses/LensesScreenCap.png)

**********************Lens Views:**********************

In Lenses you are allowed to create labels. Then when selected, the labels will highlight the main text based on how related the text is to the labels. So text more related is a darker red while text less related is lighter. This allows you to visually pick up on the relevant parts, if your mainly interested in one specific idea, you can scroll through and visually pick up on the parts. Additionally, you can have multiple lenses selected at once. So if you have a range of ideas you want to focus on, just add them.

Now lets say while reading, a particular idea in the text strikes you and you want to focus on it, well all the sentences in the text are selectable lenses! So, if you're in an abstract and see some relevant ideas, you can pick them out and go to the ones you want!

But lenses can be a bit more dynamic. One idea I found in testing was using lenses to cross off ideas. As we learn about ideas, anything we know we add to our pool of lenses and we focus on the parts which are less highlighted!

************************Map Summary:************************

The ability to zoom in and out. You can create summaries of the main text and each sentence in the summary is selectable! If an idea in the summary stands out, you can click on it and be taken to the related section in the text. So it acts as a zoomed out version and you can zoom in with the summary.

That's lenses, exploring the idea of non-linear reading. I mainly made it because there are just too many ML papers to read and I've been making tools to help me process this information much faster. Originally I was justing going to make lenses based on my notes, but I found this custom label creation to feel much better. The best feature is definitely the lens from the text, being able to pick a sentence from the text and focusing on that specific part of the paper is a godsend. Right now I still need to improve inference speed and better text processing for relevant text, specifically with pdfs. Once I work those things out and do a bit of refactoring I'll release the code.

![LensesGif1.gif](/Images/ProjectLenses/Lenses1.gif)

![LensesGif2.gif](/Images/ProjectLenses/Lenses2.gif)