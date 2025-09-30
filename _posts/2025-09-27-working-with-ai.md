---
layout: post
title: "Working with AI (not making AI work for you)"
date: 2025-09-27 10:00:00 -0500
categories: [ 'AI', 'Process' ]
listening: 'Artist: <a href="https://valleyofthesun.bandcamp.com/">Valley of the Sun</a>; Album: Volume Rock'
---

Whether I like AI or not, it is here. It is the team member that we all need to work with, whether or not we like its politics and general world view.

Therefore, it is time for me to really learn how to work with it as a thought partner. I do not want to use it to do work for me, because at my level and with the way I need to own strategy and get others on my side, I need to internalize the work. I need to continue to be a part of the work, or I can’t be smart about it and apply what I have learned.

And to be clear, I believe that the AI bubble will burst. I do not believe frontier model companies will achieve whatever they define as “AGI.” But I also believe we don’t need to. The tools we have now are powerful enough that they can’t be ignored. They are imperfect and they can not accomplish a full replacement of human labor, but they don’t have to in order to continue to have value in the economy and in knowledge work.

Here are some approaches I am trying to follow.

## Leverage NotebookLM as a conversational co-worker

A [Smashing Magazine article](https://www.smashingmagazine.com/2025/08/beyond-hype-what-ai-can-do-product-design/) answered a question I have had myself: 

> “Whenever I ask AI to suggest ideas, I just get a list of clichés. It can’t produce the kind of creative thinking expected from a product designer.”
{: .small .quote}

And its true. But everything comes down to the tool and how someone uses it. Putting too much context into a prompt will not yield better results. But leveraging a RAG model like NotebookLM puts the right context in front of the model and leads to better conversations. The article suggests three foundational documents to feed into the RAG:

+ Product Overview & Scenarios: A brief summary of what your product does and the core user scenarios.
+ Target Audience: Your main user segments and their key needs or goals.
+ Research & Experiments: Key insights from interviews, surveys, user testing, or product analytics.

Bonus points if the documents are simple text in Markdown format. AI models seem to love Markdown and the semantic clues help them break the content into semantic chunks.

Once the AI has proper context, it starts behaving more like someone who truly understands your product. The metaphor that also resonates is a really smart intern who can give you the facts but lack the experience to find the insights.

## Prototyping individual rich interactions

AI tools still struggle with long and complex user flows. Human designers are still better at this task (for now). But where AI can shine is within rich individual user interactions.

A [good article from the UX Collective on Medium](https://uxdesign.cc/figma-make-the-biggest-shift-in-ux-ui-since-sketch-5483e18f76d7) goes into detail about how Figma Make is not great for final products but can be a game changer for individual screens with complex interactivity that would normally require an engineer. The previous Smashing Magazine article has a similar example. Micro-interaction animations seem to be the right use case here, or multiple iterations on a well-defined two-stage user flow.

## Working with Large Datasets

This one is an easy win. Now that Gemini is finally available in Spreadsheets it can help do complex functions that regular users — not power users — of Excel can’t do on their own. While not perfect, sentiment analysis of non-structured data is also useful.

## Adding weird constraints to get surprising results

Sometimes you want to break out of the normal, average results. You want to be surprised. You are stuck and need a jolt that comes from a different point of view. Yes, AI can help with that.

Set up artificial limitations, or use a well-known celebrity as a POV, or require the borrowing of concepts from vastly different domains. Some examples:

+ <samp>Help me explain [X] using words a 12-year-old would understand, but make it engaging enough for experts in the field.</samp>
+ <samp>If Maya Angelou were mediating this conflict, what questions would she ask that no one else is considering?</samp>
+ <samp>Analyze my [creative project] through the lens of marine biology. What patterns or ecosystem principles could apply here?</samp>
+ <samp>This team project has 48 hours before catastrophic failure. What unconventional resources could we deploy? What rules would we break to succeed?</samp>
+ <samp>To simplify the most confusing aspect of [this project], explain my [X] strategy as if it were a board game instruction manual.</samp>

Or use the LLM as a critique engine. Ask specifically for it to point out logic holes, weak arguments, poor citations, or circular reasoning.

The author of “[5 ways to write better AI prompts](https://www.fastcompany.com/91395747/5-ways-to-write-better-ai-prompts)” distributed [a Google Doc link with other suggestion prompts](https://docs.google.com/document/d/1raFl1tsS4bSW0yjbjtBZg5u7wHN9Ep_IOaIkOkBhafE/).

## Use AI to slow down and think critically

An LLM can act as an Devil’s Advocate engine if we prompt it right. Ask it to challenge your thinking, present optional arguments, and/or consider secondary impacts or unintended consequences.

<samp>I’m planning to [decision/plan] because [reasoning] and with a goal of [objective]. Play devil’s advocate, give me multiple perspectives on this, be bold, surprising, creative, and thoughtful in your reply, and address these questions:</samp>

+ <samp>What are the strongest arguments against this approach?</samp>
+ <samp>What alternatives should I consider?</samp>
+ <samp>What risks might I be overlooking?</samp>
+ <samp>What questions should I be asking myself?</samp>
+ <samp>What challenges should I expect to face?</samp>
+ <samp>What could I do to gain more insight?</samp>
+ <samp>What could I do to increase the chances of success?</samp>

When you ask an LLM to role play like this, the language needs to underscore that you want bold thinking. LLMs want to please, so without that direction, they might opt for predictable responses. Provide as much context as you can and be detailed.

## Experiment with image generators

This is something I have not done much yet. The goal would be to create new visuals that would be used as inspiration or “design vibes,” not something that would replace a human-designed deliverable. Although, with the right tool and the right prompting, a certain level of wireframes could be possible.

Tools I have come across and need to try: 

+ Mind maps, flow charts, timelines, infographics: [MyLens](http://mylens.ai/), [Napkin](http://napkin.ai/)
+ Illustration, infographic, photos: [Ideogram](https://ideogram.cello.so/2SD2tc0B7Uc), ChatGPT, Gemini
+ Videos: Google, Sora, [Hypernatural](https://hypernatural.ai/)
