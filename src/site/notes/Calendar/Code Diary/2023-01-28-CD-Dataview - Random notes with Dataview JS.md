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
    at DataviewInlineApi.eval (plugin:dataview:18869:21)
    at evalInContext (plugin:dataview:18870:7)
    at asyncEvalInContext (plugin:dataview:18880:32)
    at DataviewJSRenderer.render (plugin:dataview:18906:19)
    at DataviewJSRenderer.onload (plugin:dataview:18448:14)
    at e.load (app://obsidian.md/app.js:1:1166483)
    at DataviewApi.executeJs (plugin:dataview:19449:18)
    at DataviewCompiler.eval (plugin:digitalgarden:10760:23)
    at Generator.next (&lt;anonymous&gt;)
    at eval (plugin:digitalgarden:90:61)
    at new Promise (&lt;anonymous&gt;)
    at __async (plugin:digitalgarden:74:10)
    at eval (plugin:digitalgarden:10699:41)
    at GardenPageCompiler.eval (plugin:digitalgarden:17175:50)
    at Generator.next (&lt;anonymous&gt;)
    at eval (plugin:digitalgarden:90:61)
    at new Promise (&lt;anonymous&gt;)
    at __async (plugin:digitalgarden:74:10)
    at eval (plugin:digitalgarden:17173:50)
    at GardenPageCompiler.eval (plugin:digitalgarden:17126:36)
    at Generator.next (&lt;anonymous&gt;)
    at fulfilled (plugin:digitalgarden:77:24)</pre>

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]