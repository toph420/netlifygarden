---
{"dg-publish":true,"permalink":"/calendar/code-diary/2023-03-08-cd-dataview-unrequited-notes/","title":"Unrequited Notes"}
---

> [!metadata]- Meta
> **up**:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> **type**:: #log/code 
> **tags**:: #on/snippets 
> **language**:: [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
> **program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> **topics**:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Unrequited Notes
**Language::**  [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**:: 

## Summary
> Query all notes not linked in this note, but that do point to this one

## Code

```datavi
list 
From #log
where contains(this.file.inlinks, file.link) and !contains(this.file.outlinks, file.link)
```

## Explanation

This is a great query that I use on my maps to show all links that point to it, but that aren't mentioned already. I still can't quite figure out if it can tell what notes are listed via a separate dataview query.

## Result

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]