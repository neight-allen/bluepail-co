---
layout: single
title: "Building an app with Generative AI"
---

[I gave a talk in the summer of 2023](https://www.youtube.com/watch?v=kNiY-HYaqUc) about how the chatbot is just an interface, and not the best interface. Well, the world seems to still be obsessed with chatbots. But I want to show that Large Language Models, Image Diffusers and even other AI models can be added to the applications we use today, and the interfaces we're already familiar with.

I'm going to build a comic book generator. I've never really been into comic books, but it should be a good example for how to build applications with Generative AI. 

- Comic books are a marriage of visual art and storytelling. We will get to use generative text and generative images.
- Each comic is made of smaller elements, like pages and panels and speech bubbles. Today's models do better with small tasks.
- It seems fun. These concepts can be used in SaaS apps, or enterprise tools, but let's get creative.

I have over a decade of experience now building applications. Through the lens of web applications is really the way that I understand software. This project is an attempt to merge my experience with what I've learned about generative AI so far. Here are some things I want to demonstrate and explore over the coming weeks:

## Product considerations

### Bookmarks, revisions and short feedback loops
In my experience with both image and text generators, you rarely get what you want on the first try. Each request you make builds on the last until you get something that kind of works. Sometimes I've gotten kind of lost in a conversation with AI, and I want to go back to something I had before. Or even start over with what I know now. So we should make it easy to iterate, bookmark promising work, and look at our past revisions as new starting points.

### The person is the primary user, the AI is secondary

Put another way: Anything an AI can do, a user can do too.

My goal is to build an interface first for the user. Then build an AI collaborator that can do things on the user's behalf. With our focus on bookmarks and revisions, we can always undo what the AI has done. This keeps the user in control, and demonstrates how to augment an existing applicaiton interface with GenAI functionality. I'm not convinced this is the only way, and I'm likely to put some "magic" into the app, but I think this is a good perspective.

### Have a specific workflow done in small chunks
The interface is split up into different activities. Storytelling is set up separate from page layout is separate from panel layout. This keeps the tasks small a managable for today's generative models. It allows you to improve your prompts at each stage. And small chunks also mean quicker iterations. 

Maybe this stifles creativity. But nothing is keeping you from jumping around. And if I know anything about users, they will go to great lengths to use your software in a way you didn't want to. but it's not unheard of in creative application. Davinci resolve has a linear workflow

## Technical considerations

### Building for experimentation
Generative AI is still hard to predict. You're going to want to try out different models and prompts and technologies. You're going to want to be able to upgrade as new things come out. I think that modularity and an agile mindset are going to be a good start, but I hope to have more strategies for this by the end of the project.

### User Feedback strategies
AI is trained. It tries to do more of what you like, and less of what you don't like. But to train it, you need data.

The first step is keeping track of what your users like and dislike. I think a lot of the existing user analytics tools out there are going to get us started. But we also need to hold on to the AI results that the user kept in their final draft, as well as things the user discarded.

Secondly, the data needs to be fed back into the AI. This might be manually updating prompts based on what users are struggling with. It might be fine tuning models with the results they landed on. It might be more manual RLHF done by someone on the development team. I'm going to try to cover a few strategies, but honestly, once you have the data collected from the previous step, there are better resources out there to help you use it.

### Copyright and Content filtering
This is the last item for a reason. I'm not particularly well versed in copyright. It's also not clear to me how, or even what we should be filtering. But I don't want to pretend that these models came out of a vacuum. They're trained on the text and images that real humans put effort into and published to the web in good faith. So, I'd like to figure out how to touch on this. Let me know if you have read some great takes lately, on either copyright or content filtering in AI.

I'm still at the begining of this journey. I don't have it all worked out yet. You'll get to see some paths that work, and some paths that don't. But if this is interesting to you, stick with me.