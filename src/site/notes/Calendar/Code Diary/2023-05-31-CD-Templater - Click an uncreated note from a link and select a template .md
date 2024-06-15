---
{"dg-publish":true,"permalink":"/calendar/code-diary/2023-05-31-cd-templater-click-an-uncreated-note-from-a-link-and-select-a-template/","title":"Click an uncreated note from a link and select a template"}
---

> [!metadata]- Meta
> **up**:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> **type**:: #log/code 
> **tags**:: #on/snippets 
> **language**:: [[Sources/Tools + Plugins/Plugin - Templater\|Templater]], [[Sources/Tools + Plugins/TypeScript\|TypeScript]]
> **program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> **topics**:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Click an uncreated note from a link and select a template 
**Language::**  [[Sources/Tools + Plugins/Plugin - Templater\|Plugin - Templater]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**URL**::

## Summary
> Did this to the new note template to create a suggested 

## Code

**My approach:**  
I have a default inbox folder for new files (core feature under files&links → default location for new notes → in specified folder).  
I set up templater (which I use anyways) to apply a template to every new note in that folder.  
This template is like follows:

```typescript
<%* let filetype = await tp.system.suggester(["Book Note", "Kanban Project", "Project Note", "Standard"], ["Book Note", "Kanban Project", "Project Note", "Standard"], false, "Which template do you want to use?") %>
<%-* if (filetype === "Book Note") { %> 
<% tp.file.include("[[Book Note Template]]") %> <% tp.file.move("/030 Media/031 Books/" + tp.file.title) %>
<%-* } else if (filetype === "Kanban Project") { %>
<% tp.file.include("[[Project Kanban]]") %> 
<%-* } else if (filetype === "Project Note") { %>
<% tp.file.include("[[Project Note Template]]") %>
<%-* } else if (filetype === "Standard") { %>
<% tp.file.include("[[New File Template]]") %>
<%-* } else { %>
<% tp.file.cursor(1) %>
<%* } -%>
```


## Explanation
Every time I create a new file in the inbox (=when I click a link to non-existing file), I get a suggester with the templates and then a file is created with the specified template.  
The book note is even moved to a specified folder. You could add this to other templates as well or use the “[auto file mover 62](https://github.com/farux/obsidian-auto-note-mover)” plugin, which had been released lately.

Sure, this is still a bit fiddly and you need to set it up for every template you like to use but it works so far for the option of clicking a link.  
Hope it helped a bit.

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]