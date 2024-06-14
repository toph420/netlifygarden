---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-13-cd-templater-using-includes-in-templater/","title":"Using Includes in Templater"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> type:: #log/code 
> language:: [[Sources/Tools + Plugins/Plugin - Templater\|Plugin - Templater]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Using Includes in Templater
**Language**:: [[Sources/Tools + Plugins/Plugin - Templater\|Plugin - Templater]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]

## Summary
> Using Templaters include function

## Code

> `tp.file.include()` doesnt require a path. Just the internal link with the title is ok. For example, if the template that you want to get the content of and added to current file has the name "fragment-Projects", just do await `tp.file.include("[[fragment-Projects]]")`. See doc.
> 
> If you want to display the content of `"[[fragment-Projects]]"`, you can do that either:
> 
> in a `<% %> `tag, i.e., `<% await tp.file.include("[[fragment-Projects]]") %>`.
> Or you can just add `tR+= await tp.file.include("[[fragment-Projects]]")` to your above script.
> 
> ```js
> if (!(await this.app.vault.adapter.exists(workdir))) {
>     await this.app.vault.createFolder(workdir);
> }
> await tp.file.move(workdir + title);  
> tR+= await tp.file.include(`[[fragment-${type}]]`);
> ```

## Explanation


## Result

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]