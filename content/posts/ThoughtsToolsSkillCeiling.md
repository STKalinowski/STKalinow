---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Thoughts: Tools & Skill Ceiling'
pubDate: 2023-07-07
description: 'Thoughts on easy to learn, hard to master.'
author: 'Stanislaw Kalinowski'
color: '16AA98'
---
I read [this great write up](https://blog.kowalczyk.info/article/2f72237a4230410a888acbfce3dc0864/lessons-learned-from-15-years-of-sumatrapdf-an-open-source-windows-app.html) by Krzysztof Kowalczyk about their experience writing SumatraPDF. One of their focuses was on simple design, with “80% of functionality with 20% of the UI.”

Note taking, with pen and paper, follows this rule, if not more so. Its ink on paper, but the possibilities are endless! We create our own writing and note taking system, system of marking, staring, and highlighting. The act of writing is simple, but the expressive ness is high.

But this idea only focuses on accessibility, make users immediately do what they want.

Game design has an idea of skill floor and skill ceiling. Skill floor focuses on entry level players, ones just starting. Having a low skill floor means its easy for anyone to pick up and play the game. A high skill floor means players need to learn much more before they can grasp the game. This 80/20 UI rule centres around creating a low skill floor, make it easy for new users to use the app. 

But there is the idea of skill ceiling, how much can possibly be done/expressed. Games with high skill ceiling means players have a lot to learn before they truly mastered the game. In the context of apps and UI, a high skill ceiling means the user can do a lot with the tool. Think of drawing or animating tools, they provide many options and functionality, which means there is much to master.

Preferably, game devs aim for the combination of both a low skill floor and high skill ceiling. “Easy to learn, hard to master”

Pen & paper follows this paradigm. Its easy to draw and take note, and there is plenty of room for expression and mastery.

Thinking about designs in my own applications. I wrote about fluid designs before, and how LLMs can create dynamic interfaces for users, custom. I also wrote about how applications designed around LLMs need to be correctable, because they are making some level of assumptions. 

So I should design around easy to use parts, giving only a core set of options. But these options should allow for a degree of expression. For my flash card application I'm working on, it generates cards using LLMs, I guess I should focus on creating a core set of generation blocks the user can use, and let the user create their complexity by combining these blocks.