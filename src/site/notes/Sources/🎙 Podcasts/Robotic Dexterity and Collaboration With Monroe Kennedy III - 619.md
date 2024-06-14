---
{"dg-publish":true,"permalink":"/sources/podcasts/robotic-dexterity-and-collaboration-with-monroe-kennedy-iii-619/"}
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
>> **Title**:: Robotic Dexterity and Collaboration With Monroe Kennedy III - #619
>> **URL**:: "https://share.snipd.com/episode/a57e945b-b10e-4aa8-a366-922f40ea4db8"
>> **Reviewed Date**:: [[Calendar/Journal/Daily/2023-03-06\|2023-03-06]]
>> **Finished Year**:: [[2023\|2023]]


# Robotic Dexterity and Collaboration with Monroe Kennedy III - #619


![Cover|200](https://wsrv.nl/?url=https%3A%2F%2Fmegaphone.imgix.net%2Fpodcasts%2F35230150-ee98-11eb-ad1a-b38cbabcd053%2Fimage%2FTWIML_AI_Podcast_Official_Cover_Art_1400px.png%3Fixlib%3Drails-4.3.1%26max-w%3D3000%26max-h%3D3000%26fit%3Dcrop%26auto%3Dformat%2Ccompress&w=200&h=200)


## Episode metadata
- Episode title:: [[Robotic Dexterity and Collaboration with Monroe Kennedy III - #619\|Robotic Dexterity and Collaboration with Monroe Kennedy III - #619]]
- Show:: [[The TWIML AI Podcast (formerly This Week in Machine Learning & Artificial Intelligence)\|The TWIML AI Podcast (formerly This Week in Machine Learning & Artificial Intelligence)]]
- Owner / Host:: [[TWIML\|TWIML]]
- Episode link:: [open in Snipd](https://share.snipd.com/episode/a57e945b-b10e-4aa8-a366-922f40ea4db8)
- Episode publish date:: 2023-03-06
<details>
<summary>Show notes</summary>
> Today we’re joined by Monroe Kennedy III, an assistant professor at Stanford, director of the Assistive Robotics and Manipulation Lab, and a national director of Black in Robotics. In our conversation with Monroe, we spend some time exploring the robotics landscape, getting Monroe’s thoughts on the current challenges in the field, as well as his opinion on choreographed demonstrations like the dancing Boston Robotics machines. We also dig into his work around two distinct threads, Robotic Dexterity, (what does it take to make robots capable of doing manipulation useful tasks with and for humans?) and Collaborative Robotics (how do we go beyond advanced autonomy in robots towards making effective robotic teammates capable of working with human counterparts?). Finally, we discuss DenseTact, an optical-tactile sensor capable of visualizing the deformed surface of a soft fingertip and using that image in a neural network to perform calibrated shape reconstruction and 6-axis wrench estimation.<br/>>  The complete show notes for this episode can be found at twimlai.com/go/619.
</details>

- Show notes link:: [open website](https://twimlai.com/podcast/twimlai/robotic-dexterity-and-collaboration/)
- Tags: #podcasts #snipd
- Export date:: 2023-03-06T23:12


## Snips


### [03:47] The Future of Robotics: Collaborative Partnerships


[🎧 Play snip - 1min️ (02:04 - 03:51)](https://share.snipd.com/snip/8fa1d04f-1a0a-413c-b438-430155148404)
<audio controls> <source src="https://chrt.fm/track/4D4ED/traffic.megaphone.fm/MLN3901987359.mp3?updated=1678129643#t=02:04,03:51"> </audio>


### ✨ Key takeaways
1. Robots are becoming increasingly capable and able to complete tasks that are difficult or dangerous for humans.
2. The next step is to see if they can be good teammates for human collaborators, and help make life safer and easier for people.


#### 📚 Transcript
> [!quote]- Transcript
> 
> **Speaker 1**
> Absolutely. A perfect way to think about this paradigm is first through, think about all the aspects of robotics and where we've come to to date. If you kind of back up to the 80s and the 90s, you have these robots that you see in factories that are helping you to assemble cars and these other big tasks, doing tasks that are really unsafe for people but very repetitive. So the robots didn't have to really have a good understanding of their environment. They just had to move accurately and precisely. If you kind of fast forward this to the 2000s, early 2000s, you see robots really being used for autonomy. So now they have to be able to sense their environment, understand their place in the environment and what they should be doing to accomplish a particular task. This goes from ground robots to aerial vehicles and then ultimately even multi-robotics systems working together became the space of robotics, the leading edge, the cutting edge. Now we're on this new horizon where we're saying if we have these very capable autonomous systems, can they actually be good teammates for possibly human collaborators? How can they make human life better, safer and longer through their activities? And so when you specifically think about what these hard tasks might include, you can ask yourself, well, if I had a robot in my home right now, what do I think would potentially be too challenging for them to complete? So many people have rumbas, you can see them driving around and performing vacuuming tasks, those are pretty straightforward. And you have a dishwasher, right, that's able to clean your dishes fairly well but you still have to put the dishes in the dishwasher, you still have to move your furniture around so that and pick things up off the floor so your rumba doesn't vacuum up the strings in your rug or something.




---


### [06:19] The Role of Dexterity in Robotics


[🎧 Play snip - 1min️ (04:37 - 06:17)](https://share.snipd.com/snip/0a04619f-d7e6-4cf5-80ad-d3c1623eabd5)
<audio controls> <source src="https://chrt.fm/track/4D4ED/traffic.megaphone.fm/MLN3901987359.mp3?updated=1678129643#t=04:37,06:17"> </audio>


### ✨ Key takeaways
1. Dexterity is important for robots when it comes to folding clothes and other tasks.
2. The process of turning a robot on and choreographing it to do flips is not as simple as it seems.


#### 📚 Transcript
> [!quote]- Transcript
> 
> **Speaker 2**
> Awesome. So you mentioned folding clothes and I remember seeing it CES probably three something actually. I always have to add three pandemic years. Exactly. And so it's probably more like six years ago. Some company demoed their clothes folding robot and the thing spent maybe 10 minutes to fold a t-shirt or something like that. And you're looking at it and you're like, man, that's so easy for us and it's so hard for this robot. It sounds like dexterity and perception around dexterity are as your answer to why it's so hard.
>
> **Speaker 1**
> Absolutely. Absolutely. And so you could take any one of these scenarios and just really just expand on that. And if you kind of dig in, it's really easy to see how that the role that dexterity plays in those abilities. Mm-hmm. Yeah.
>
> **Speaker 2**
> On this thought of kind of why don't we see robots around doing these things. One thing that we do frequently see are these amazing videos from Boston Dynamics about now robots jumping around and doing flips. And I always like to ask folks who are deep in the field, like, you look at these things and they give the impression that they turn the robot on and say, hey, run around this course and do some flips. And when I talk to folks in the know, at least historically, it's always been, yeah, it's really much more tightly choreographed than that, what's your take on kind of what's happening behind the scenes and how close they are to kind of this autonomous future for those kinds of robots.
>
> **Speaker 1**
> It's a fantastic question.




---


### [06:45] Why do we see robots doing flips and other amazing feats, but they are still not really autonomous?


[🎧 Play snip - 1min️ (05:14 - 06:47)](https://share.snipd.com/snip/efa00914-28e7-42c7-a956-5812a863a5f5)
<audio controls> <source src="https://chrt.fm/track/4D4ED/traffic.megaphone.fm/MLN3901987359.mp3?updated=1678129643#t=05:14,06:47"> </audio>


### ✨ Key takeaways
1. Dexterity is important for robots to be able to do complex tasks such as jumping and flipping.
2. There is a lot of choreography that goes into making these demonstrations successful.


#### 📚 Transcript
> [!quote]- Transcript
> 
> **Speaker 1**
> Absolutely. Absolutely. And so you could take any one of these scenarios and just really just expand on that. And if you kind of dig in, it's really easy to see how that the role that dexterity plays in those abilities. Mm-hmm. Yeah.
>
> **Speaker 2**
> On this thought of kind of why don't we see robots around doing these things. One thing that we do frequently see are these amazing videos from Boston Dynamics about now robots jumping around and doing flips. And I always like to ask folks who are deep in the field, like, you look at these things and they give the impression that they turn the robot on and say, hey, run around this course and do some flips. And when I talk to folks in the know, at least historically, it's always been, yeah, it's really much more tightly choreographed than that, what's your take on kind of what's happening behind the scenes and how close they are to kind of this autonomous future for those kinds of robots.
>
> **Speaker 1**
> It's a fantastic question. And I would have to agree with the consensus that there is a lot of choreography that's going into making these types of demonstrations successful, but kind of thinking about why, right? To go from where they are to a robot that's truly capable to do this reliably, consistently and can adapt to uncertainty to kind of frame that. It's good to understand in robotic autonomy, there's three main parts, right? There's the see, the think and the act. So seeing is perception.




---


### [08:07] The Art of Robotic Demonstrations


[🎧 Play snip - 1min️ (06:15 - 08:10)](https://share.snipd.com/snip/0f291910-e4ea-4df5-bbe5-980c99ee2c7c)
<audio controls> <source src="https://chrt.fm/track/4D4ED/traffic.megaphone.fm/MLN3901987359.mp3?updated=1678129643#t=06:15,08:10"> </audio>


### ✨ Key takeaways
1. There is a lot of choreography that goes into making demonstrations successful, but it is important to understand why these demonstrations work in order to create reliable robots that can adapt to uncertainty.
2. Perception in robotics is important, as it includes taking observation of the world from sensors and converting it into a state that the robot can understand. The think part of the equation is intelligence, and the act is control.


#### 📚 Transcript
> [!quote]- Transcript
> 
> **Speaker 1**
> It's a fantastic question. And I would have to agree with the consensus that there is a lot of choreography that's going into making these types of demonstrations successful, but kind of thinking about why, right? To go from where they are to a robot that's truly capable to do this reliably, consistently and can adapt to uncertainty to kind of frame that. It's good to understand in robotic autonomy, there's three main parts, right? There's the see, the think and the act. So seeing is perception. How do you perceive your world? How do you take observation of your space from sensors, be it cameras or touch sensors and convert whatever raw sensing you have into a state that you can then say, this is what I want to be a particular thing, right? This is a consistent dimension, a consistent representation of the world and myself and what I want that to ultimately become. And then becomes the think, which is the intelligence and the planning, right? Possibly AI that says, how do I take that state representation that I perceived in my world and then figure out what I should do next in order to achieve an objective or a goal and then is my act or control? How do I take that goal, that objective, my current state and drive the state that I'm at to my desired state? And so when you look at a system like that, there's of course the see, think, act control loop, but a lot of the perception is internal. So it says, given the robots, motors and joints, what is my current orientation, right? What is my current velocity? And that's well and good if you're in a very manufactured environment that's excluded to the task that you're trying to complete. But often as we know as humans, the real world is uncertain. The ground may not be always perfectly flat. Your foot may trip or catch on a piece of an object. And when that little bit of disturbance happens, right?




---


### [11:23] The Role of Artificial Intelligence in Robotics


[🎧 Play snip - 1min️ (09:38 - 11:21)](https://share.snipd.com/snip/978b1492-7510-460c-88ce-e58971f4717c)
<audio controls> <source src="https://chrt.fm/track/4D4ED/traffic.megaphone.fm/MLN3901987359.mp3?updated=1678129643#t=09:38,11:21"> </audio>


### ✨ Key takeaways
1. Robotics still has a lot of hardware and sensor creation problems to solve.
2. AI is a useful tool for adapting to uncertainty in the real world.
3. Machine learning is a useful tool for adapting to uncertainty in the real world.


#### 📚 Transcript
> [!quote]- Transcript
> 
> **Speaker 1**
> I think that's a great overview and I kind of go back to what I described for students in terms of the whole trajectory and space of robotics. I think the hardware and construction is still a very important problem. You need these reliable systems to accomplish what you want. So I mentioned dexterity before. One question you might have is, well, how do we make fingers that are similar to humans and can give you the information to extract the state that you want? So there's a really big hardware and sensor creation problem that's still being solved. How do we create an analog to human hands that's truly reliable and robust? That doesn't really exist yet and at an affordable price. And then once you have that, then it's that C-Think Act. But the thing is, right, when you think about the more complex tasks you want to do or I give you these really fancy sensors that may have computer vision involved, the question becomes how do you appropriately model that? And I think that's the real trajectory that's brought us to AI now because go back a few decades, a lot of the things we were doing with robots may have been well represented by analytical expressions. But the moment we think about the real world and being robust and reliable in these scenarios, we need to be able to adapt to uncertainty. And if I program my robot and I put it in the real world and I'm trying to model some aspect of the world, that model that I developed when I'm sitting at my computer and programming, if I made it an analytical expression, may not correctly reflect the real world when the robot gets there. And so the beauty of artificial intelligence machine learning is it presents a set of fundamental tools that can actually learn models from data. So I can observe the real world. I can see what happens when I take particular action and then I can adapt.




---


### [12:59] The Role of Dexterity in Collaborative Robotics


[🎧 Play snip - 1min️ (11:58 - 13:01)](https://share.snipd.com/snip/fd54e709-4132-42ca-8caf-a818162ce60a)
<audio controls> <source src="https://chrt.fm/track/4D4ED/traffic.megaphone.fm/MLN3901987359.mp3?updated=1678129643#t=11:58,13:01"> </audio>


### ✨ Key takeaways
1. Dr. Ravi has been working on a research program to address the problems of dexterity for collaborative robots,.
2. One of the key challenges is robot sense of touch.


#### 📚 Transcript
> [!quote]- Transcript
> 
> **Speaker 2**
> Yeah, yeah, let's dig a little bit deeper into the work you're doing around dexterity. How have you kind of built out a research program to push that aspect of the field forward?
>
> **Speaker 1**
> Yeah, so that's a great question. So when I first got here, I was working with my students and we wanted to address what we thought were the big problems that we're keeping collaborative robots from being in people's homes. And while there are a lot of problems to solve that are not completely solved yet in terms of locomotion, perception in terms of vision and motion and hand dexterity, we believe that one of the key aspects right now, one of the key challenges, robot sense of touch. If you look at a lot of what humans are able to do, we rely on our sense of touch to a very large degree. We have mechanical receptors in our fingers that are able to give us information about pressure, texture, forces, and all of that information goes back to our brain and we can do very complex dexterous tasks with that information. And robots don't have that analog yet. So within dexterity, there's two main trains of thought.




---


### [15:08] Dense Tack: A Robotic Finger Tip Sensor


[🎧 Play snip - 1min️ (13:41 - 15:14)](https://share.snipd.com/snip/99ac81e9-e004-44e5-8c3c-0f739b9541de)
<audio controls> <source src="https://chrt.fm/track/4D4ED/traffic.megaphone.fm/MLN3901987359.mp3?updated=1678129643#t=13:41,15:14"> </audio>


### ✨ Key takeaways
1. Dense tack is an optical tactile sensor that is different from other sensors in the family because it can modularize the process of transferring information from images to an interpretable intermediate output.
2. This would allow a robot to adapt to tasks that seem similar, but are actually more complex than they appear.


#### 📚 Transcript
> [!quote]- Transcript
> 
> **Speaker 1**
> So my lab, we developed a robotic finger tip called dense tack. It's an optical tactile sensor in the family of these types of sensors. So there's quite a few out there you'll see in this space. What really sets ours apart is we said, well, if you look at a lot of work in this space with these types of optical tactile sensors, these are extremely powerful because they let you see the finger tip and you can actually use that information to potentially plan how you should move your fingers and your joints and even higher level plans of how to do a manipulation task, but when you want to extend that to a new task, if you're going directly from the fingertip images to some complex manipulation task, that's called an end to end method, it's often very hard to transfer that ability from one task to another, even if the tasks are relatively similar. So if I'm opening up a large water bottle versus a tiny water bottle adapting to something that to us seems extremely similar can be very complex for the robot. So what we want to do is modularize that process. Can I go from the images that are received by my sensor to an interpretable intermediate output or state, which tells me what is the three dimensional shape that's calibrated over the surface of my sensor? What is the net force on that sensor and soon what is the stress vector field over that sensor? And if we can get there, then we can actually leverage 20 years of robotic research that did this type of analysis for point models.




---


### [17:44] The Effect of Touch on Brain Activity


[🎧 Play snip - 58sec️ (16:52 - 17:50)](https://share.snipd.com/snip/4a1b546f-0fe8-4890-81d6-fcc7a0b813a7)
<audio controls> <source src="https://chrt.fm/track/4D4ED/traffic.megaphone.fm/MLN3901987359.mp3?updated=1678129643#t=16:52,17:50"> </audio>


### ✨ Key takeaways
1. Touch can be interpreted visually through cameras.
2. Touch can still trigger a response in the brain even when not physically touched.


#### 📚 Transcript
> [!quote]- Transcript
> 
> **Speaker 1**
> Absolutely, absolutely. And there's a paper and I can find the reference quickly that was really interesting. There was a study. And in this study, they had individuals look at their hand through a camera as they touched their hand to provide some force. You could see this through a camera and they were monitoring their brains with like an MRI machine. And so they would touch your finger and then the part of your brain that cortex that gives you information when you receive touch with fire, right? But this particular study said, well, what if we turn the sensitivity up really, really, really high for the MRI as we're doing this? And then we touch a few times, but then sometimes we show their hand being touched on the video, right, without actually touching their hand. What happens in that part of the brain? Yeah. And what was really cool was the part of the brain that fires due to physical touch fired very slightly due to visual observation.




---


### [22:26] The Advantages of Using Visual Sensors Over Physical Sensors for Thread Identification


[🎧 Play snip - 1min️ (21:02 - 22:26)](https://share.snipd.com/snip/5383ba8a-d87c-4b50-813f-dc27253ff883)
<audio controls> <source src="https://chrt.fm/track/4D4ED/traffic.megaphone.fm/MLN3901987359.mp3?updated=1678129643#t=21:02,22:26"> </audio>


### ✨ Key takeaways
1. Using visual sensors is a better way to detect small screws than using tactile sensors because the resolution is high.
2. Piezole resistive sensors are a popular way to detect small screws, but they have limitations.


#### 📚 Transcript
> [!quote]- Transcript
> 
> **Speaker 2**
> Yeah, just to play devil's advocate on that use case, like if I've got this manipulator that can dig into the bowl and pull out a screw, why can't I just add an 11th camera that looks at the screw and does all the things that you want to do in the visual domain without the tactile domain?
>
> **Speaker 1**
> I think the conception you have in your mind right now of this is that the screw is so large that if you're holding it in your hand, an external camera would be able to see it. But the screws we're dealing with are so small, we're dealing with small screws that are so small that when our fingers push together, you can't see them from the outside. Got it.
>
> **Speaker 2**
> And yet you're able to, with these tactile sensors, still resolve thread pitch and all that stuff?
>
> **Speaker 1**
> Yeah, that's crazy. We treat those as like a pattern that we're able to see on the inside of our image and then you can form pattern recognition and recognize your screw thread. I think that kind of further supports using visual sensors because the resolution that short distance is going to be very high as opposed to like some matrix of physical sensors that is exactly and never be able to do that with these very small screws. Absolutely. And that's such a great point because this is the leading challenge. You mentioned that piezole resistive sensor you can have. That's been a very popular method.




---





Created with [Snipd](https://www.snipd.com) | Highlight & Take Notes from Podcasts


---
up:: [[Atlas/📥 Sources\|📥 Sources]]

