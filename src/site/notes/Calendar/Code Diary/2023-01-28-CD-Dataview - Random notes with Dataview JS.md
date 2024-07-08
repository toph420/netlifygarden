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
> <pre class="dataview dataview-error">Evaluation Error: eval@[native code]
@
@
asyncFunctionResume@[native code]
@
asyncFunctionResume@[native code]
onload@
@capacitor://localhost/app.js:1:1171693
@
asyncFunctionResume@[native code]
@
generatorResume@[native code]
@
Promise@[native code]
__async@
@
generatorResume@[native code]
@
Promise@[native code]
__async@
generatorResume@[native code]
fulfilled@
promiseReactionJob@[native code]</pre>

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]