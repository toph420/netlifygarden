---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-13-cd-dataview-keeping-notes-on-beers/","title":"Keeping Notes on Beers"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> type:: #log/code 
> tags:: #to/implement 
> language:: [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]], [[Sources/Tools + Plugins/JavaScript\|JavaScript]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Keeping Notes on Beers
**Language::**  [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]], [[Sources/Tools + Plugins/JavaScript\|JavaScript]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**::[DataviewJS Snippet Showcase - Obsidian Forum](https://forum.obsidian.md/t/dataviewjs-snippet-showcase/17847/137)

## Summary
> Track and display metadata with dataviewjs

## Code
> **Keeping notes on Beers**
> 
> Final example i’d like to showcase, is how I use dataviewjs for styling in my Beer notes.
> 
> I’m an occasional beer drinker, love trying different ones, always forget which I like and where I got them. For ages I wanted to be able to have a personal way of keeping track of what I liked and disliked, but at the same time, have it quick to do, otherwise I won’t do it. After a bit of refining i’ve settled on a note template that works well for me that looks something like this:
> 
> ![image](https://forum.obsidian.md/uploads/default/optimized/3X/f/3/f3cd348c8fe1e747008e24791d0ceeb952e35a3e_2_385x500.jpeg)
> 
> With the code looking like this:
> 
> ````swift
> ---
> type: beerCard
> Rating: 9
> ABV: 6.5%
> Cost: £
> Producer: Pressure Drop
> Type: Porter
> Bought-From: "[[Beer and Burger]]"
> Tasting-Notes: "Great porter, really balanced flavour, not to sweet and can taste the coffee and chocolate. Really easy drinker. Would definitely get again"
> Image: "[[IMG_20220107_230609.jpg]]"
> Description: "Roasty, Coffee Chocolate"
> ---
> 
> Tags: #products/beer 
> 
> \``` dataviewjs
> // Nicely Render all the inlinks to the current note on a single line
> // Checks if an alias exists for inlinks and will render the alias
> // if it exists
> //
> let myInlinks = [];
> for (let inlink of dv.current().file.inlinks){
> 	let inlinkFile = dv.page(inlink.path).file
> 	let displayName = inlinkFile.aliases ? inlinkFile.aliases[0] : inlinkFile.name
> 	let fileLink = dv.fileLink(inlinkFile.path, false, displayName)
> 	myInlinks.push(fileLink)
> }
> let myInlinksStr = `**Inlinks**: ${myInlinks.join(', ')}`
> dv.paragraph(myInlinksStr)
> \```
> **Oulinks**: [[_MOC Products|Products]], [[Beer Tasting Notes]]
> 
> # Fashion Porter
> 
> ``` dataviewjs
> let page = dv.current();
> dv.paragraph(
> 	"**Description** " + page.Description
> )
> \```
> 
> ![[IMG_20220107_230609.jpg|left|250]]
> \``` dataviewjs
> let page = dv.current();
> 
> dv.paragraph(
> 	"**Rating:** " + page.Rating + "\n"
> 	+ "**ABV:** " + page.ABV + "\n"
> 	+ "**Cost:** " + page.Cost + "\n"
> 	+ "**Type:** " + page.Type + "\n"
> 	+ "**Producer:** " + page.Producer + "\n"
> 	+ "**Bought From**: " + page["Bought-From"] + "\n"
> 	+ "**Tasting Notes**: " + page["Tasting-Notes"]
> )
> \```
> ````
> 
> So when I create a new beerCard note, I just update the YAML and take a quick picture of the beer on my phone and import into the note.
> 
> And since it’s all in the metadata… I get to create a pretty dataview table like this:
> 
> ![image](https://forum.obsidian.md/uploads/default/optimized/3X/a/9/a9a0d0cb819189bda5ac1a4b6ab0c8b1cf5cac75_2_690x447.png)
> N.B. If you look close you’ll see a few minor inconsistencies in the code snippets across my showcases, since my templates and queries get a bit more evolved. Ultimately Obsidian is a tool for capturing knowledge for me so I try not to be too disciplined or care too much about the underlying consistency unless I have a reason too.

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]