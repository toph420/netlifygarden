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

<pre class="dataview dataview-error">Evaluation Error: SyntaxError: Unexpected identifier 'to'
    at DataviewInlineApi.eval (plugin:dataview:18885:21)
    at evalInContext (plugin:dataview:18886:7)
    at asyncEvalInContext (plugin:dataview:18896:32)
    at DataviewJSRenderer.render (plugin:dataview:18922:19)
    at DataviewJSRenderer.onload (plugin:dataview:18464:14)
    at e.load (app://obsidian.md/app.js:1:1166749)
    at DataviewApi.executeJs (plugin:dataview:19465:18)
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