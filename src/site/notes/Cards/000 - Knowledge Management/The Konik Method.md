---
{"dg-publish":true,"permalink":"/cards/000-knowledge-management/the-konik-method/","title":"The Konik Method"}
---

> [!metadata]- Meta
> **up**:: [[Cards/000 - Knowledge Management/Taking Notes\|Taking Notes]], [[Cards/000 - Knowledge Management/000 - Knowledge Management\|Knowledge Management]]
> **type**:: #📝 
> **status**:: #📝/🌲 
> **tags**:: #on/pkm, #on/obsidian 
> **topics**::  [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> **links**:: [[Sources/📰 Articles/The Konik Method for Making Useful Notes\|The Konik Method for Making Useful Notes]]


# The Konik Method for Making Useful Notes
- [Eleanor's Readwise Settings · GitHub](https://gist.github.com/eleanorkonik/1f0586fe13d98f1dbf18ec72b00bf37d)


- Start with a **why**
	- Pleasure reading
	- I have a question, problem solving
	- Passive feeds
- Pre-existing notes: 
	- **Logs and indexes**
		- Lists of things (books to read, places to go)
		- Concept notes (Chinese infrastructure, The Bronze Age)
	- **Claims/evidence/explanations**
		- Given file names that are claims
		- Think a flash card with the claim as the title and the other side has links to citations, longer explanation of how the info is useful, and my own ideas about how I can use it
		- Always attribute the source, and don't necessarily paraphrase in your own words. Attribution errors are naughty. 

> [!tip]  Example of attribution using a callout:
>
> > [!quote] [Title](app://obsidian.md/link) by [author](app://obsidian.md/author) via [publication](app://obsidian.md/publication). Published on date. Accessed on today.  
> > Text of the quote.
> 
> - [N] Brief explanation of why I saved this quote, and any other associated thoughts it gave me about connections, expansions, etc. The annotation, basically.
> - [?] A question about this 

Example of a [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]] query that sorts pending sources by size of the file. The thinking is that the larger the file, the more useful info.
```datavie
TABLE file.inlinks AS Inlinks, file.outlinks AS Outlinks, file.tags AS Tags  
FROM "Sources" and #📥/🟥   
WHERE length(file.inlinks) > 0 OR length(file.outlinks) > 1 Or length(file.tags) > 2  
SORT file.size ASC
```

- Eleonor uses a unique identifier in highlight headings to save her in case she changes the heading text by accident. 
	- I don't (now I do) do this, time will tell if I should have 🤷‍♂️
- Make sure the highlights are useful and make sense
- Add notes, tags, links, reminders in Reader. Often the highlights are not knowledge, but rather an action item to do something specific with the highlight. 
- Engaging with your highlights
	- Paraphrasing to avoid plagiarism isn't useful. 
	- Consider the quote evidence for a claim
		- Quotes that can be used for multiple claims should be broken into smaller pieces


> [!tip] Example Highlight
>  ### id286148681 Nomads make cheese to preserve milk
>     
>  > Zandee did not know the nomads’ language, so his friend Gulzar translated as Zandee asked how much they made from selling the cheese. “Nothing,” Gulzar said. “They just do it so that the milk will not go stale. At most, they will barter it with a shopkeeper who may give them a pound of sugar or a dozen matchsticks.”
>  
>   `nomads make cheese to preserve milk`, or perhaps `nomads make cheese to avoid wasting milk` which is wordier but also more accurate.


- Turning Highlights into notes
	1. Make a new note and name it after your claim ie `Nomads make cheese to avoid wasting milk`
	2. Embed the section into your new note: `![[The Kashmiri Cheese Brand Operating at 7,000 Feet by Safina Nabi#id286148681 nomads make cheese to avoid wasting milk]]`
		- To quickly get the section, copy the id and start typing `![[##id12345`
		- *This helps because you don't need to search down through all the `nomad` headings*
	3. Move annotations to a new note and add connections. Creating these claims removes the obfuscation of the highlight, bringing it into the index of search. No more digging through sources to find the highlight/annotation.
		- Using the [[Sources/Tools + Plugins/Plugin - Quickadd\|Plugin - Quickadd]] Zettelizer script you can quickly turn these highlights and annotations into new notes! 
		- After processing the pending source it's moved to the References folder and marked as synthesized.
- Use the notes!

---
up:: [[🏠 Home\|🏠 Home]]

