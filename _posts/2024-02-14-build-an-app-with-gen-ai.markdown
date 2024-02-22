---
layout: single
title: "Building an app with Generative AI"
share: true
---

![A vibrant celebration between a human and a robot](/assets/images/robots-and-humans-working-together.png)

[I gave a talk in the summer of 2023](https://www.youtube.com/watch?v=kNiY-HYaqUc) about how the chatbot is just an interface, and not always the best interface. Well, the chatbot obsession rages on. I want to show that Large Language Models, Image Diffusers and other AI models can augment the applications we use today using interfaces we're already familiar with.

To explore this idea, I plan to build a comic book studio. A browser based application that lets you write and illustrate your own comic book, but with the help of Generative AI. Here's a few reasons why I keep coming back to this idea:

- Comic books are a marriage of visual art and storytelling. That gives me the opportunity to use both generative text and generative images.
- Each comic is made of smaller elements, like pages and panels and speech bubbles. Today's models do better with small tasks.
- It seems fun. AI can be used in SaaS apps, or enterprise tools, but let's get creative.

Personally, I've never really been into comic books, but it should be a good way to experiment with GenAI in traditional interfaces.

--------------------

I have over a decade of experience building applications. My understanding of software is through the lens of web applications. This project is an attempt to merge that experience with practical uses of Generative AI. Here are some things I hope to demonstrate and explore over the coming weeks:

## Product considerations

### Bookmarks, revisions and short feedback loops
In my experience with GenAI, you rarely get what you want on the first try. But each prompt builds on the last until you get something that kind of works. At times, I'll get something that works for my needs, but I continue to experiment only to realize my best result was 10 prompts ago. Sometimes I want to start over after some experimentation.

It should be easy for the user to iterate, bookmark promising results, restore past revisions, build on past successes and, if needed, start over.

### AI is a tool, not a replacement
My goal is to build an interface first for the user. Then build an AI collaborator that can do things on the user's behalf. With our focus on bookmarks and revisions, we can always undo what the AI has done. This keeps the user in control, and demonstrates how to augment an existing application interface with GenAI functionality. I'm not convinced this is the only way, and I'm likely to put some "magic" into the app, but I think this is a good perspective.

### Define a step by step workflow
I imagine different layouts for different activities. Storytelling is set up separate from page layout is separate from panel layout. This keeps the tasks small a manageable for today's generative models. It allows you to iterate your prompts at each stage. And smaller tasks for the AI also means quicker feedback to the user.

### There can still be a chatbot
I'm actually really excited the way that OpenAI has incorporated things like functions and the ability to write and run code. Chat functionality is going to be a lower priority for this project, but I'm not taking the stance that chatbots have no place. Just that they're restrictive as the sole way to interact.

## Technical considerations

### Building for experimentation
Results from generative AI are still hard to predict. Developers need to try out different models and prompts and technologies. They need to be able to upgrade as new things come out. I think that modularity and an agile mindset are going to be a good start, but I hope to have more strategies by the end of the project.

### User Feedback strategies
AI is trained. It tries to do more of what you like, and less of what you don't like. But in order to train, you need data.

The first step is keeping track of what users like and dislike. I think existing user analytics tools are going to get us started. But we also need to hold on to the AI results that the user keeps, as well as things the user discarded.

Secondly, data needs to be fed back into the AI. This might be manually updating prompts based on what users are struggling with. It might be fine tuning models with the results they landed on. It might be more manual RLHF done by someone on the development team. I'm going to try to cover a few strategies, but there also are good resources already for creating better prompts from known examples or fine tuning models.

### Can we work toward the Rails of GenAI?

Django and Ruby on Rails were both developed by building out an application, and then generalizing the architecture. Whatever I build is going to be really rough, but I hope to learn enough that I could start to see how a GenAI framework might help other developers build their own GenAI applications. And I would love for other developers to help me with that vision.

### Copyright and Content filtering
This is the last item for a reason. I'm not particularly well versed in copyright. It's also not clear to me how, or even what we should be filtering. But I don't want to pretend that these models came out of a vacuum. They're trained on the text and images that real humans put effort into and published to the web in good faith. And I don't want to wildly miss user expectations on text and images that could be considered offensive. So, I'd like to figure out how to touch on this. Let me know if you have read some great takes lately, on either copyright or content filtering in AI.

---------------------

I'm still at the beginning of this journey. I don't have it all worked out yet. You'll get to see some paths that work, and some paths that don't. But if this is interesting to you, stick with me.