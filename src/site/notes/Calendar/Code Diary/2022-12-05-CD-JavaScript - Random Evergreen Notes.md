---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-05-cd-java-script-random-evergreen-notes/","title":"Random Evergreen Notes"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> type:: #log/code 
> language:: [[Sources/Tools + Plugins/JavaScript\|JavaScript]], [[Sources/Tools + Plugins/Plugin - Templater\|Plugin - Templater]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Random Evergreen Notes
**Language::**  [[Sources/Tools + Plugins/JavaScript\|JavaScript]], [[Sources/Tools + Plugins/Plugin - Templater\|Plugin - Templater]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]

## Summary
> This script will insert 5 random 🌲 evergreen notes upon creation of new note with the included template

## Code

- Include this in the desired note template:
```
<% tp.file.include("[[Template, Random Evergreen]]") %>
```

- Make a "Template, Random Evergreen.md" file and add this:
```js
<%* 
    const randomEvergreenNotes = []

    app.metadataCache.getCachedFiles().forEach(filename => { // get all filenames in the vault and iterate through all of them, calling a function for each of them
	let { tags } = app.metadataCache.getCache(filename) // get the tags in the  file w/ the given name
    tags = (tags || []).filter(t => t.tag && "#evergreen" === t.tag) // filter out all tags that are not "#evergreen"
        
    if (tags.length > 0) { 
	  randomEvergreenNotes.push(filename.slice(13, filename.length - 3)) // removes first 13 characters (03-evergreen/) then cuts off last three characters from filename (.md)
        }
    })

	// loop through and display 5 random notes
    var i = 0
    do {
        const randomIndex = Math.floor(Math.random() * randomEvergreenNotes.length)
        tR += `- [[${randomEvergreenNotes[randomIndex]}]]` + "\r\n"
        i++
    } while (i<5)
%>
```

## Explanation
- 

## Result
- ![Pasted image 20221205190554.png](/img/user/Extras/Attachments/Pasted%20image%2020221205190554.png)
---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]