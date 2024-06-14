---
{"dg-publish":true,"permalink":"/sources/podcasts/ai-trends-2023-reinforcement-learning-rlhf-robotic-pre-training-and-offline-rl-with-sergey-levine-612/"}
---

> [!multi-column]
>
>> [!metadata]- Meta
>> **up**:: [[Atlas/📥 Sources\|📥 Sources]]
>> **type**:: #📥/🎙 
>> **status**:: #📥/🟥 
>> **tags**:: #on/podcasts
>> **topics**::  
>
>> [!metadata]- Podcast Info
>> **Author**:: The TWIML AI Podcast (formerly This Week in Machine Learning & Artificial Intelligence)
>> **Title**:: AI Trends 2023 —  Reinforcement Learning - RLHF, Robotic Pre-Training, and Offline RL With Sergey Levine - #612
>> **URL**:: https://share.snipd.com/episode/e223f8df-4287-4efb-806d-2bd2f6801fda
>> **Reviewed Date**:: [[2023-01-16 \|2023-01-16 ]]
>> **Finished Year**:: [[2023\|2023]]

# AI Trends 2023 —  Reinforcement Learning - RLHF, Robotic Pre-Training, and Offline RL With Sergey Levine - #612

## Highlights
> Learning From Human Preferences in Reinforcement Learning
> Transcript:
> Speaker 1
> Not that important kind of just about anything would do the job there.
> Speaker 2
> Has RLHF as a technique are you aware of other places that it's been applied beyond instruct GPT and chat GPT?
> Speaker 1
> Well, so the idea of learning from human preferences in reinforcement learning is actually very old, but perhaps the modern incarnation of that idea first came to the forefront. I think this was roughly five years ago in the context of more standard RL problems like these little like local motion and simulation tasks and work by Paul Cristiano who described this algorithm, like the optometrist algorithm for doing it basically show the human to trials, ask them which one they prefer. Yeah, exactly. And then use that to back out a reward signal. And that work itself is like somewhat old classical. And there's work on preferences going further than that. In fact, arguably the foundation of the notion of rewards and utilities in reinforcement learning really comes down to preferences. Like the way you define a rational agent, an agent is rational if it has preferences that satisfy an ordering. So if I prefer like, you know, bananas over apples and apples over oranges, then I should really prefer bananas over oranges. And if it's the other way around, if my preferences are inconsistent, then I am not a rational agent. That's basically the definition of rationale. And there's a classical theorem that says that if you have preferences that obey an ordering, then there exists a scalar value utility function, basically a reward

> Learning From Human Preferences in Reinforcement Learning
> Transcript:
> Speaker 1
> Of learning from human preferences in reinforcement learning is actually very old, but perhaps the modern incarnation of that idea first came to the forefront. I think this was roughly five years ago in the context of more standard RL problems like these little like local motion and simulation tasks and work by Paul Cristiano who described this algorithm, like the optometrist algorithm for doing it basically show the human to trials, ask them which one they prefer. Yeah, exactly. And then use that to back out a reward signal. And that work itself is like somewhat old classical. And there's work on preferences going further than that. In fact, arguably the foundation of the notion of rewards and utilities in reinforcement learning really comes down to preferences. Like the way you define a rational agent, an agent is rational if it has preferences that satisfy an ordering. So if I prefer like, you know, bananas over apples and apples over oranges, then I should really prefer bananas over oranges. And if it's the other way around, if my preferences are inconsistent, then I am not a rational agent. That's basically the definition of rationale. And there's a classical theorem that says that if you have preferences that obey an ordering, then there exists a scalar value utility function, basically a reward function that will reflect those preferences. If you open up Stuart Russell's AI textbook, like the classic textbook, it's called artificial intelligence like that is the definition of a rational agent.
> Speaker 2
> Do you think that the enthusiasm around chat GBT and
---
up:: [[Atlas/📥 Sources\|📥 Sources]]
