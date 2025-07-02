---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-21-cd-javascript-get-the-current-notes-inlinks-with-dvjs/","title":"Get the current notes inlinks with DVJS"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> categories:: #log/code 
> language:: [[Sources/Tools + Plugins/JavaScript\|JavaScript]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Get the current notes inlinks with DVJS
**Language::**  [[Sources/Tools + Plugins/JavaScript\|JavaScript]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**:: [[Calendar/Code Diary/2022-12-13-CD-Dataview - Keeping Notes on Beers\|2022-12-13-CD-Dataview - Keeping Notes on Beers]]

## Summary
> Use Dataview JS to get the current notes inlinks

## Code

```js 
// ^ (change to dvjs to use)
// Nicely Render all the inlinks to the current note on a single line
// Checks if an alias exists for inlinks and will render the alias
// if it exists
//
let myInlinks = [];
for (let inlink of dv.current().file.inlinks){
	let inlinkFile = dv.page(inlink.path).file
	let displayName = inlinkFile.aliases ? inlinkFile.aliases[0] : inlinkFile.name
	let fileLink = dv.fileLink(inlinkFile.path, false, displayName)
	myInlinks.push(fileLink)
}
let myInlinksStr = `**Inlinks**: \n - ${myInlinks.join('\n-  ')}`
dv.paragraph(myInlinksStr)
```

## Explanation

## Result

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]