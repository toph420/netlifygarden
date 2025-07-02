---
{"dg-publish":true,"permalink":"/calendar/code-diary/2023-01-23-cd-dataview-dataview-tabs/","title":"Dataview Tabs"}
---

> [!metadata]- Meta
> **up**:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> **type**:: #log/code 
> **tags**:: #on/snippets 
> **language**:: [[Sources/Tools + Plugins/Plugin - Dataview\|Dataview]]
> **program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> **topics**:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Dataview Tabs
**Language::**  [[Dataview\|Dataview]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**::

## Summary
> Use Dataview JS to generate tabs and their respective tab pages

## Code
```js (change to dataviewjs to use)
const createButton = (name) => {
	const btn = dv.el('button', name)
	btn.addEventListener('click', (event) => {
		event.preventDefault()
		removeTable()
		renderTable(name)
	})
	
	return btn
}

const buttons = ['#📥/🟥', '#📥/🟧', '#📥/🟨', '#📥/🟩']


const renderTable = (name) => {
	const pages = dv.pages('"Sources"').where(page => page.status == name).where(page => page.type != '#📥/🛠').sort(page => page.file.cday, "desc")
	dv.table(
	['Title', 'Summary', 'Rating', 'Type'], 
	pages.map(page => [page.file.link, page.summary, page.rating, '<span class=center-block>' + page.type.slice(4) + '</span>']))
}

const removeTable = () => {
	this.container.lastChild.remove()
}

buttons.forEach(button => createButton(button))

renderTable('#📥/🟥')
```

## Result

> [!example]+ Tabs
> <pre class="dataview dataview-error">Evaluation Error: SyntaxError: Unexpected token '&gt;'
    at DataviewInlineApi.eval (plugin:dataview:19027:21)
    at evalInContext (plugin:dataview:19028:7)
    at asyncEvalInContext (plugin:dataview:19038:32)
    at DataviewJSRenderer.render (plugin:dataview:19064:19)
    at DataviewJSRenderer.onload (plugin:dataview:18606:14)
    at e.load (app://obsidian.md/app.js:1:1204966)
    at DataviewApi.executeJs (plugin:dataview:19607:18)
    at DataviewCompiler.eval (plugin:digitalgarden:10760:23)
    at Generator.next (&lt;anonymous&gt;)
    at eval (plugin:digitalgarden:90:61)</pre>


---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]