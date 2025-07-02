---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-09-cd-java-script-display-obsidian-notes-in-a-table-using-dvjs/","title":"Display Obsidian notes in a table using DVJS"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> categories:: #log/code 
> tags:: #on/dataview 
> language:: [[Sources/Tools + Plugins/JavaScript\|JavaScript]], [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Display Obsidian notes in a table using DVJS
**Language::**  [[Sources/Tools + Plugins/JavaScript\|JavaScript]], [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]

## Summary
> Josh's video is a great use case for Obsidian and a few commenters left some great Dataview snippets

## Code

Comment from Dovos: *"most of the js code is not necessary. a dv.markdownTable() function that works the same as a dv.table() function would have been enough and would give the same result. here is a cleaner version of your code that works either as markdown table or as [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]] table"*

```js
// ^ Change to dataviewjs to run

const pg = dv.current()
const header = ["Name", "Base", "Slow", "Normal", "Fast"]
let data = []

for (let move of Object.entries(pg.movement)){
	data.push([
		move[1].name, 
		move[1].base, 
		move[1].slow, 
		move[1].normal, 
		move[1].fast
	])
}

dv.paragraph(dv.markdownTable(header, data)) 		//this gives out the result as a markdown table
dv.table(header, data) 							//this gives out the result as a dataview table

```

## Explanation
- Lists metadata of the current note in a table

## Result

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]