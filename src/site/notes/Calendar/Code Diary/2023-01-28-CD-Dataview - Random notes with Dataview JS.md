---
{"dg-publish":true,"permalink":"/calendar/code-diary/2023-01-28-cd-dataview-random-notes-with-dataview-js/","title":"Random notes with Dataview JS"}
---

> [!metadata]- Meta
> **up**:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> **type**:: #log/code 
> **tags**:: #on/snippets 
> **language**:: [[Sources/Tools + Plugins/Plugin - Dataview\|Dataview]]
> **program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> **topics**:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# 
**Language::**  [[Dataview\|Dataview]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**::

## Summary
> Display random notes using Dataview JS

## Code

```dataviewj
const numberToShow = 5;
const notes = dv.pages('#📝/🌞 and -"Calendar"') 
.sort(() => 0.5 - Math.random()) 
.slice (0, numberToShow) 
.map (note => note.file.link); 
dv.list(notes);
```

## Result


> [!code] Result
> <pre class="dataview dataview-error">Evaluation Error: SyntaxError: Unexpected token '&gt;'
    at DataviewInlineApi.eval (plugin:dataview:19027:21)
    at evalInContext (plugin:dataview:19028:7)
    at asyncEvalInContext (plugin:dataview:19038:32)
    at DataviewJSRenderer.render (plugin:dataview:19064:19)
    at DataviewJSRenderer.onload (plugin:dataview:18606:14)
    at DataviewJSRenderer.load (app://obsidian.md/app.js:1:1204966)
    at DataviewApi.executeJs (plugin:dataview:19607:18)
    at DataviewCompiler.eval (plugin:digitalgarden:10763:23)
    at Generator.next (&lt;anonymous&gt;)
    at eval (plugin:digitalgarden:90:61)</pre>

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]