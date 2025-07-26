---
{"dg-publish":true,"permalink":"/sources/tools-plugins/plugin-dataview/"}
---


> [!metadata]- Meta
> up:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> categories:: #📥/🛠   
> tags:: #on/pkm, #on/plugins #on/obsidian 
> status:: #📥/🟧 
> links:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]
> links:: [[Atlas/🧠 My Vault\|🗳 My Vault]], [[Sources/Tools + Plugins/Tools + Plugins\|Tools + Plugins]]

# Dataview

- [Dataview Docs](https://blacksmithgu.github.io/obsidian-dataview/)
- [Dataview Example Vault](https://s-blu.github.io/obsidian_dataview_example_vault/)
- [[Dataview Queries Overview\|Dataview Queries Overview]] - all sorts of queries right here in this vault

## Resources 
- [Napkinium's Dataview Examples](https://publish.obsidian.md/napkinium/Index)
- [Dataview Query builder](https://s-blu.github.io/basic-dataview-query-builder/)
- [Adding Metadata - Using fields](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/)
- [Bases Toolbox](https://bases-toolbox.vercel.app/#dataview-converter) - convert data view to bases


## Miscellaneous Snippets
See [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]] for more


> [!code] Common
> **Backlinks**
> ```
> LIST
> FROM [[Nanotechnology]]
> and !outgoing([[Nanotechnology]])
> SORT file.link asc
> ```

> [!code]- DVJS
> **Currently reading**
> ```js
> dv.table(["Cover","Name", "Author", "Genre", "Rating","Progress"], dv.pages("#reading")
>     .map(b => [("![](" + b.cover + ")"), b.file.link, b.author, b.genre, (b.rating + "🌟"), b.status]))
> ```
> 
> **Sources where rating > 7, group by status** 
> ```js
> dataviewjs
> let pages = dv.pages("#source").where(b => b.rating >= 7);
> for (let group of pages.groupBy(b => b.status)) {
>    dv.header(3, group.key);
>    dv.list(group.rows.file.link);
> }
> ```
> **Type by Status**
> ```js
> dataviewjs
> for (let group of dv.pages('"Spaces/Ducks Films/Projects"').where(p => p.type === "project").groupBy(c => c.status)) {
> 	dv.header(5,group.key)
> 	dv.table(["status","client"],
> 	group.rows
> 		.where(p => p.client === "")
> 		.sort(p => p.client)
> 		.map(p => [p.file.link,p.client]))
> }
> ```
> **Get project summaries from each project**
> ```js 
> dataviewjs
> const header = '## Summary'
> 
> // You can update this to filter as you like
> const pages = dv.pages("#projects")
> 
> // This regex will return text from the Summary header, until it reaches
> // the next header, a horizontal line, or the end of the file
> const regex = new RegExp(`\n${header}\r?\n(.*?)(\n#|\n---|$)`, 's')
> 
> for (const page of pages) {
>     const file = app.vault.getAbstractFileByPath(page.file.path)
>     // Read the file contents
>     const contents = await app.vault.read(file)
>     // Extract the summary via regex
>     const summary = contents.match(regex)
>     if (summary) {
>         // Output the header and summary
>         dv.header(3, file.basename)
>         dv.paragraph(summary[1].trim())
>     }
> }
> ```
> **List and group notes tagged with `#to/do` tags**
> ```js
> dataviewjs
> let todoTags = [
> 	"#to/do/write",
> 	"#to/do/program",
> 	"#to/do/conceptualize",
> 	"#to/explore/read",
> 	"#to/explore/watch",
> 	"#to/explore/research",
> 	"#to/ponder/me",
> 	"#to/ponder/society"
> ]
> 
> function getLastEdited(page) {
> 	return (page);
> }
> 
> for (let tag of todoTags) {
> 	dv.table([tag, "Last Edited", "Created"], dv.pages(tag).where( p =>
> 			p.file.name != "my TO(DO) and EVER(GREEN) structure"
> 		).map(p => [
> 			p.file.link,
> 			getLastEdited(p.file.mtime),
> 			p.file.ctime
> 		]))
> }
> ```

---
up:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]