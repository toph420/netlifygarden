---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-13-cd-dataview-show-unresolved-links/","title":"Show unresolved links"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> categories:: #log/code 
> language:: [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Show unresolved links
**Language::**  [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**:: [DataviewJS Snippet Showcase - Obsidian Forum](https://forum.obsidian.md/t/dataviewjs-snippet-showcase/17847/146)

## Summary
> See all your dangling links, great for cleaning up your vault

## Code
> 
> This snippet allows you to see all your dangling links.  
> 
> You can configure how many connections each link has to have before it shows up.  
> 
> You can also exclude existing and non-existing files from showing up.
> 
> ```javascript
> //how many links a non existing file should have at minimum
> const count = 2;
> 
> //specify the full path here.
> const ignoredExisting = ["your/ignored/notes/here.md"];
> 
> //keep these in lower case.
> const ignoredNonExisiting = ["your non exisiting notes", "here is note that does not exist"];
> 
> let d = {};
> function process(k, v) {
>   Object.keys(v).forEach(function (x) {
>     if(!ignoredNonExisiting.includes(x.toLowerCase())) {
>         x = dv.fileLink(x);
>         if (d[x]==undefined) { d[x] = []; }
>         if(!ignoredExisting.includes(k)) {
>             d[x].push(dv.fileLink(k));
>         }
>     }
>   });
> }
> 
> Object.entries(dv.app.metadataCache.unresolvedLinks)
>     .filter(([k,v]) =Object.keys(v).length)
>     .forEach(([k,v]) =process(k, v));
>     
> dv.table(["Non existing notes", "Linked from"],
>          Object.entries(d)
>          .filter(([k, v]) =v.length >= count)
> 	     .sort((a, b) =b[1].length - a[1].length)
>          .map(([k,v]) =[k, v.join(" • ")]));
> ```
> 
> (code based on: [Is there a way to see backlinks without creating a markdown document? - #3 by JLDiaz 14](https://forum.obsidian.md/t/is-there-a-way-to-see-backlinks-without-creating-a-markdown-document/26977/3))

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]