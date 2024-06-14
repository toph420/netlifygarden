---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-04-cd-java-script-quickadd-example/","title":"Quickadd Example"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> type:: #log/code 
> language:: [[Sources/Tools + Plugins/JavaScript\|JavaScript]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]], [[Sources/Tools + Plugins/Plugin - Quickadd\|Quickadd]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Quickadd Example
**Language::**  [[Sources/Tools + Plugins/JavaScript\|JavaScript]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]

## Summary
> undefined

## Code
```JavaScript
const projectNotes = DataviewAPI.pages("#project").where(p => !p.file.path.contains("Template")).values;
const targetProject = await this.quickAddApi.suggester(projectNotes.map(p => p.file.name), projectNotes);
const targetProjectFile = app.vault.getAbstractFileByPath(targetProject.file.path);
let markdownLink = this.app.fileManager.generateMarkdownLink(targetProjectFile, '');
markdownLink = `${markdownLink.slice(0, markdownLink.length - 2)}|${targetProject.alias}${markdownLink.slice(markdownLink.length - 2)}`
return `Project:: ${markdownLink}`;
```

## Explanation
- 

## Result

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]