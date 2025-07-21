---
{"dg-publish":true,"permalink":"/sources/tools-plugins/plugin-templater/","title":"Plugin - Templater","tags":["📥","📥/🛠","on/plugins"]}
---



# Templater
> All things related to Templater

## Notes
- [[Sources/Tools + Plugins/Obsidian Scrapers\|Obsidian Scrapers]] - docs for scraping from the web
- [[Sources/📰 Articles/Shabeblog Templater Snippets\|Shabeblog Templater Snippets]]

## Guides
- [Syntax - Templater](https://silentvoid13.github.io/Templater/syntax.html)
- [Snippets - Templater](https://github.com/SilentVoid13/Templater/discussions/categories/templates-showcase)
- [Simplified one-line templates - YouTube](https://www.youtube.com/watch?v=9q-kmiyE168&t=399s)

## My Scripts
- Extras/Templates/Templater
- See [[Sources/📰 Articles/How to Use Templater JS Scripts 1\|How to Use Templater JS Scripts 1]] by [[Shabeblog\|Shabeblog]]
- `<%* tp.user.updateTitle(tp) %>` 
	- When placed in a template it will check if the file name includes "Untitled" or "Undefined", if so it will prompt for a new file name.

## Temporal

-   Todays Date `<%tp.date.now("YYYY-MM-DD")%>`
-   Todays Date Offset `<%tp.date.now("YYYY-MM-DD", -1)%>`
-   Todays Date Custom Week `<%tp.date.now("YYYY-[W]ww", 7)%>`
-   Todays Date Custom Month `<%tp.date.now("YYYY-[M]MM", 28)%>`
-   Todays Date Custom Year

## Cursors

`<%tp.file.cursor(1)%>` this one immediately gets replaced by cursor if the number is 1

additional ones denoted by number order you must "Tab" through with the templater keybinding which i have mapped to `⌥+Tab`

`<%tp.file.cursor(2)%>`

## Prompts

`<%tp.system.prompt("What is my name", "TOPHER")%>`

## Logic / Control Flow

Basically JavaScript Functions:

```javascript
if (tp.file.tags.contains("#todo")) {
	"This is a todo file !"
} else {
	"This is a finished file !"
}
```

```javascript
<%* if (tp.file.tags.contains("#todo")) { %>
This is a todo file !
<%* } else { %>
This is a finished file !
<%* } %>
```

```
can also use `else if`

```javascript
<%* if (1==2) { %>
if result
<%* } else if (1==1) { %>
else if result
<%* } else { %>
else result
<%* } %>
```

Can also use arbitrary [JavaScript](https://publish.obsidian.md/bryan-jenks/JavaScript):

```javascript
<%* if (tp.file.title.charAt(0) == "{") { %>
<%tp.file.cursor(1)%><%tp.file.include("Templates/Inputs/Book")%>
<%* } else if (tp.file.title.charAt(0) == "=") { %>
<%tp.file.cursor(1)%><%tp.file.include("Templates/Inputs/Thought")%>
<%* } else { %>
<%tp.file.cursor(1)%><%tp.file.include("Templates/Inputs/New")%>
<%* } %>
```

in here the result of the `tp` api is getting the file name to the `tp.file` object that has a property `.title` so we're getting the first character of that title with pure Javascript through: `.charAt(0)`

putting it all together: `tp.file.title.charAt(0)`

## Examples

[SilentVoid13/Templater · GitHub](https://github.com/SilentVoid13/Templater/discussions/categories/templates-showcase) - GitHub Repo of Templater examples including:

```ad-note

### Choose Folder and create file by template
*When creating a note with this in the template it will prompt for a folder and title*

	<%*
		const folders = this.app.vault.getAllLoadedFiles().filter(i => i.children).map(folder => folder.path);
		const folderPath = await tp.system.suggester(folders, folders);
		const title = await tp.system.prompt("Title")
		await tp.file.rename(`${title}`)
		await tp.file.move(`/${folderPath}/${title}`)
	%>
```

```ad-note

### Rename and move file to specific folder
``` javascript
<%*
//If File is untitled prompt the User to set a Title (Source: https://github.com/SilentVoid13/Templater/discussions/259)
let title = tp.file.title
if (title.startsWith("Untitled")) {
    title = await tp.system.prompt("Title") ?? "Untitled";
    await tp.file.rename(`${title}`);
} %>
date: "<% tp.file.creation_date("dddd Do MMMM YYYY HH:mm") %>"
topic: <% tp.file.cursor(1) %>
tags:
  - <% tp.file.folder() %>/<% tp.file.cursor(1) %>
aliases: []
<%*
//If this File is in my English Folder set the language correctly. I assume it will be German otherwise
//This is mostly for the Dictionary Plugin Integration
if(tp.file.folder() === "Englisch") {
	tR += "language: en-US";
} else {
	tR += "language: de";
} %>
---

# <% tp.file.title %>

<% tp.file.cursor(2) %>

```

---

up:: [[Sources/Tools + Plugins/Tools + Plugins\|Tools + Plugins]]
