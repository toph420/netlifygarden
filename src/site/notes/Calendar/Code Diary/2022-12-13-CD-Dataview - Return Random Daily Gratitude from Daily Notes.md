---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-13-cd-dataview-return-random-daily-gratitude-from-daily-notes/","title":"Return Random Daily Gratitude from Daily Notes"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> categories:: #log/code 
> language:: [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]], [[Sources/Tools + Plugins/JavaScript\|JavaScript]]
> tags:: #to/implement 
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Return Random Daily Gratitude from Daily Notes
**Language::**  [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]], [[Sources/Tools + Plugins/JavaScript\|JavaScript]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**:: [Return Random Daily Gratitude from Daily Note Pages - Obsidian Forum](https://forum.obsidian.md/t/return-random-daily-gratitude-from-daily-note-pages/34352#what-im-trying-to-do-2)

## Summary
> Get the values of an inline field, randomize, and return

## Code
> 
> ### Things I have tried
> 
> -   Creating a simple DataView list with one line selected at random from a specified inline field, but DataView does not appear to have a “random” function.
> -   Using [Dice Roller plugin 10](https://github.com/valentine195/obsidian-dice-roller) to pull random lines, but it doesn’t read DataView tables when generating results.
> 
> ### What I’m trying to do
> 
> Every day, in my Daily Notes Page, I write down two things for which I am grateful using the custom field "Gratitude:: " e.g.
> 
> ```rust
> Gratitude:: I am grateful for the Obsidian forum community.
> Gratitude:: I am also grateful for the hard work others have put in to making Obsidian what it is today.
> ```
> 
> What I would like to do, as a pick-me-up, is put a random "Gratitude:: " block in a note that serves as my homepage so I can have regular reminders to be grateful, selected at random from my own statements. When I open the page, the block might read “Remember, I am grateful for the Obsidian forum community” one day, but “Remember, I am also grateful for the hard work others have put in to make Obsidian what it is today.” another.
> 
> If there’s no way to get DataView to pull a random result, is there a way to export a DataView list or table to a new note so I could use the Dice Roller plugin?

**Answer:**
> Adding the source page doesn’t take much extra code; instead of storing just the message, we store an object that contains both the message and the page it came from:
```js
// List of gratitudes
let gratitudes = [];

// Extract gratitudes from pages that have them
dv.pages()
	.where(page => page.gratitude)
	.forEach(page => {
		dv.array(page.gratitude)
			.forEach(gratitude => {
				gratitudes.push({
					message: gratitude,
					page: page
				});
				})});

let greeting = gratitudes[Math.floor(Math.random()*gratitudes.length)] 

dv.paragraph(greeting.message + " - " + greeting.page.file.link);
```
Result: 
![Pasted image 20221213204239.png](/img/user/Extras/Attachments/Pasted%20image%2020221213204239.png)

**Users Implementation:**
```js
// List of gratitudes
let gratitudes = [];

// Extract gratitudes from pages that have them
dv.pages()
	.where(page => page.gratitude)
	.forEach(page => {
		dv.array(page.gratitude)
			.forEach(gratitude => {
				gratitudes.push({
					message: gratitude,
					page: page
				});
				})});

// List of awesome things
let somethingawesomes = [];
// Extract awesome things from pages that have them
dv.pages()
	.where(page => page.somethingawesome)
	.forEach(page => {
		dv.array(page.somethingawesome)
			.forEach(somethingawesome => {
				somethingawesomes.push({
					message: somethingawesome,
					page: page
				});
				})});

let gratitudegreeting = gratitudes[Math.floor(Math.random()*gratitudes.length)] 
let awesomegreeting = somethingawesomes[Math.floor(Math.random()*somethingawesomes.length)]

dv.paragraph("*A random awesome thing:* " + awesomegreeting.message + " (" + awesomegreeting.page.file.link + ")" + "<br>" + "*Practice gratitude:* " + gratitudegreeting.message + " (" + gratitudegreeting.page.file.link + ")");
```



## Result
![Pasted image 20221213204107.png](/img/user/Extras/Attachments/Pasted%20image%2020221213204107.png)

## Explanation
> It works like a charm, and it’s so good! Thank you very much!
> 
> I actually use two writing exercise as part of my daily journaling practice, one is to write down two things I’m grateful for at the beginning of the day and the other is to write down something awesome that I noticed by the end of the day. As much as I love gratitude journals and inspirational quotes, I felt like they would be much more meaningful coming from my own life, even if I’m not as eloquent as others who might write such prompts.
> 
> In any case, I was able to modify the code you provided (I think the page.link.file was where I was getting stuck) and I couldn’t be happier with the results. Now, if I want to revisit something awesome or a particular moment of gratitude, the link is right there! I’m sharing the snippet I use below in case other people find themselves wanting to do something similar.
---

up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]