---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Thoughts: Best flashcards I have written.'
pubDate: 2023-08-03
description: 'Space repetition as a feedback mechanism.'
author: 'Stanislaw Kalinowski'
color: 'A1C45A'
---
I am a big believer in spaced repetition as a study method. I like it's guaranteed process of learning. By far one of my favorite concepts for flash carding is writing what I call mistake or error cards. 

Whenever I make a mistake or fail at something, I add a card for it. It's usually something along the lines of how a bug was introduced into the code or why I struggled with something I was studying. I try to add cards for even simple and honest mistakes things like forgetting to put a log in a data processing loop. 

I like this concept because it's using my flash carding system (used to be Anki, but now I'm writing my own Fiszka) as a guaranteed feedback mechanism. And writing cards for errors feels natural. The errors happened for a reason and I need to reinforce myself to try to avoid it. There have been plenty of time where I learn the solution but still mess up in future occurrences. This is a way to guarantee that I address it, and I don't have to worry about it, I know my program will show and repeat the card if necessary!

An important thing to note is that the cards should be structured in a generalized manner. Instead of writing a card like "What as the bug introduced in project x?", cards should attack the aspect of why and how the bug occurred. We aren't trying to remember the bug, but think about the general solution.

An example if how I had a program simulating a model, and I was using tinkter for the first time. Each frame consisted of a pass through a model and then copy and display it. But it seems I forgot I was running it in a different process, and so the frame was being saved to the local space, and was therefore being cleared right away. I could just write a card "What was the bug preventing frames from updating?". But better cards would address the problem. "Why did the frames not render?", "{Mini example}, What is the bug?", "How does the gc in python trigger?". There is nothing wrong with remember a particular moment, but generalized cards are more transferable.

I think these are my most valuable cards because they come directly from experiences where I do need reminder. They are places I messed up, and adding them guarantees I fix it. It's better than note taking, because my program forces me to address it while notes can be passed over and forgotten. I would recommend any else with a memory practice to pick up the same habit.