---
{"dg-publish":true,"permalink":"/extras/templates/template-map/","title":"<% tp.file.title %>","tags":["🗺️",{"{ VALUE:Map Tag - ie on/tag }":null}]}
---


<%*
const title = tp.file.title;
if (title.includes("Untitled")) {
	const newTitle = await tp.system.prompt("File Name");
	await tp.file.rename(newTitle);
}
-%>

# <% await tp.file.title %>

> {{VALUE:Summary}}

> [!Example]+ Jumping off points
> *List a few of the most important <% tp.file.title %> related notes*


> [!Links]+ 💧 Raindrop Bookmarks on AI
> <iframe style="border: 0; width: 100%; height: 450px;" allowfullscreen frameborder="0" src="{{VALUE:Raindrop Link}}"></iframe>

---
up:: [[{VALUE:Parent Link}}\|{VALUE:Parent Link}}]]

