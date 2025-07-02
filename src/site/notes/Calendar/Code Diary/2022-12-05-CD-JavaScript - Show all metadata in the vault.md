---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-05-cd-java-script-show-all-metadata-in-the-vault/","title":"Show all metadata in the vault"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> categories:: #log/code 
> language:: [[Sources/Tools + Plugins/JavaScript\|JavaScript]], [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Show all metadata in the vault
**Language::**  [[Sources/Tools + Plugins/JavaScript\|JavaScript]], [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]

## Summary
> Use DVJS to show all the metadata in the vault

## Code
```js
const pagelimit = 5;
const metadataMap = {};

dv.pages().forEach(page => {
    Object.keys(page).forEach(metadata => {
        if (metadata === 'file') return;
        metadata = metadata.toLowerCase().replaceAll(" ", "-")
        if (!metadataMap[metadata]) {
            metadataMap[metadata] = []
        }
        if (!metadataMap[metadata].some(l => l.path === page.file.link.path)) {
            metadataMap[metadata].push(page);
        }
    })
})

dv.table(["meta data", "page count", `pages (first ${pagelimit})`, "Values"], Object.keys(metadataMap).sort().map(key => (
[key, 
 metadataMap[key].length, 
 dv.array(metadataMap[key]).file.link.limit(pagelimit), 
 dv.array(metadataMap[key]).limit(pagelimit)[key]
 ])))
```

## Explanation
- 

## Result

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]