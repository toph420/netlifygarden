---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-10-cd-dataview-list-items-containing-a-certain-tag/","title":"List items containing a certain tag"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> type:: #log/code 
> language:: [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# List items containing a certain tag
**Language::**  [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]

## Summary
> List all bullet points that contain a certain tag

## Code

```datavie
LIST WITHOUT ID L.text
FROM #log 
FLATTEN file.lists AS L
WHERE contains(L.tags, "#🔗")
```

## Explanation
- 

## Result

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]