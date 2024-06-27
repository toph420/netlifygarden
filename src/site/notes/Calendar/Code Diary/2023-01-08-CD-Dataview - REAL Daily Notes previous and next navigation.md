---
{"dg-publish":true,"permalink":"/calendar/code-diary/2023-01-08-cd-dataview-real-daily-notes-previous-and-next-navigation/","title":"REAL Daily Notes previous and next navigation"}
---

> [!metadata]- Meta
> **up**:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> **type**:: #log/code 
> **language**:: [[Dataview\|Dataview]]
> **program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> **topics**:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# REAL Daily Notes previous and next navigation
**Language::**  [[Dataview\|Dataview]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**:: https://forum.obsidian.md/t/dataviewjs-snippet-showcase/17847/23?u=gibson

## Summary
> Real previous and next links for daily notes

## Code
```js (change to dvjs to use)
/*
    previous/next note by date for Daily Notes
    Also works for other files having a `date:` YAML entry.
    MCH 2021-06-14
*/
var none = '(none)';
var p = dv.pages('"' + dv.current().file.folder + '"').where(p => p.file.day).map(p => [p.file.name, p.file.day.toISODate()]).sort(p => p[1]);
var t = dv.current().file.day ? dv.current().file.day.toISODate() : luxon.DateTime.now().toISODate();

// Obsidian uses moment.js; Luxon’s format strings differ!
var format = app['internalPlugins']['plugins']['daily-notes']['instance']['options']['format'] || 'YYYY-MM-DD';
var current = '(' + moment(t).format(format) + ')';
var nav = [];
var today = p.find(p => p[1] == t);
var next = p.find(p => p[1] > t);
var prev = undefined;
p.forEach(function (p, i) {
    if (p[1] < t) {
        prev = p;
    }
});
nav.push(prev ? '[[' + prev[0] + ']]' : none);
//nav.push(today ? today[0] : none);
nav.push(today ? today[0] : current);
nav.push(next ? '[[' + next[0] + ']]' : none);

//dv.list(nav);
//dv.paragraph(nav.join(" · "));
dv.paragraph(nav[0] + ' ← ' + nav[1] + ' → ' + nav[2]);
```

## Result

<pre class="dataview dataview-error">Evaluation Error: eval@[native code]
@
@
asyncFunctionResume@[native code]
@
asyncFunctionResume@[native code]
onload@
@capacitor://localhost/app.js:1:1170964
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