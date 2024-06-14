---
{"dg-publish":true,"permalink":"/cards/000-knowledge-management/my-meta/","title":"My Meta"}
---

> [!metadata]- Meta
> up:: [[Atlas/🧠 Sid\|🗳 My Vault]]
> type:: #⚙️
> tags:: #on/pkm, #on/workflow
> status:: #📝/🌱
> topics:: [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]], [[Sources/Tools + Plugins/Plugin - Templater\|Plugin - Templater]], [[Cards/000 - Knowledge Management/000 - Knowledge Management\|000 - Knowledge Management]]
> links:: [[Cards/000 - Knowledge Management/Workflows/My Note Taking Workflow\|My Note Taking Process]]

# My Meta
> All things related to the metadata attached to my notes. 

- [[Cards/000 - Knowledge Management/Workflows/My Note Taking Workflow\|My Note Taking Process]]

## Tags

All top level “tags” ie log, map, project are all “types” of notes and when necessary the “type” field should be included in a note. 

Some tags nested values mark a “status,” others mark a further classification of the “type”

All notes, regardless of “type” contain a `#📝` node throughout its journey as it matures into a `#📝/🌲`, which is the ultimate goal. 

See [[Cards/000 - Knowledge Management/Obsidian Vaults/Petrichors Vault\|Petrichors Vault]] for inspiration

```
#⚙️  Utility (dont think I use this)
#log 
	#log/event 
	#log/journal 
	#log/meeting 
	#log/code 
	#log/dream 
	#log/idea
	#log/condition 
	#log/week 
	#log/year 
#🗺 
	- #🗺/view 
#📝 
	- #📝/🥀 (weed)
	- #📝/🌞 (incubator)
	- #📝/🌱 (sprout)
	- #📝/🌿 (sapling)
	- #📝/🌲 (evergreen)
#on (similar to topic, but high level)
	- #on/readme 
	- #on/workflow 
	- #on/VideoEditing 
	- #on/obsidian 
	- #on/readme 
	- #on/x
#project
	- #project/🟥 (backlog)
	- #project/🟨 (in progress)
	- #project/🟩 (completed)
	- #project/⬛️ (archived)
	- #project/newsletter
	- #project/marketing
	- #project/video
	- #project/video/wedding 
	- #project/video/recap 
#📥
	- #📥/🟥 (not processed)
	- #📥/🟧 (processing)
	- #📥/🟨 (synthesizing)
	- #📥/🟩 (completed)
	- #📥/🛠 (tool)
	- #📥/🎥 (video)
	- #📥/📰 (article)
	- #📥/📚 (book)
	- #📥/🐦 (tweet)
	- #📥/🔗 (link)
	- #📥/🎙 (podcast)
	- #📥/💭 (my thoughts on a source)

#concept — 📜 
#person - 👽
#company - 🛸
#client - 🤑
#private - 👀

Also inline tags for tasks and list items (for work use Todoist)
#🔥 (fire shit)
#🧠 (obsidian)
#💡 (idea)
#🔗 (link)
#📸 (image)
#🎥 (video)
#to (ie read, explore, implement)
```

## Source Tags
See:: [[Cards/000 - Knowledge Management/Workflows/My Note Taking Workflow\|My Note Taking Process]]
- `#📥/📰` Article
	- Use highlights chrome extension to help create these article types for articles from medium
- `#📥/🎥` Video
	- YouTube, Vimeo. Import using the [[Sources/Tools + Plugins/Obsidian Scrapers\|Obsidian Scrapers]] to use the clipboard to auto fill the template and [[Youtube Summarizer\|Youtube Summarizer]]
- `#📥/🐦` Tweet
	- Readwise gets confused with tweets due to all of the formatting and characters, it’s best to manually add tweets and threads and be selective, often times the threads link to the real information, not just headlines.
- `#📥/🛠` Tool
	- Various useful tools. Link keywords!
- `#📥/📽` Movie
	- [ ] Pull from Letterboxd using scrapers and a new AI prompt 
- `#📥/📚` Book
	- Learn to read 😂
- `#📥/👨‍🏫`
	- This could turn into a big one, I’d like to build an index of tutorials, maybe by using `📥/👨‍🏫/editing`
	- Include project files for the tutorials and bundle once tutorial turns `📥/🟩` or when a tag of `#files`

## Project (`#project`)
1. Quickadd macro "Create New Ducks Project"
2. Frontmatter fields:
	1. `title:`
	2. `aliases: []`
	3. `created: 2022-10-26`
	4. `modified:`
	5. `due:`
	6. `completed:`
	9. `storage:`
	10. `summary:` 
3. Meta
	1. `type: #project`
	2. `status: #project/ 🟥, #project/🟨, #project/🟩, #project/⬛`
	3. `client:`
		1. get the value of a "person" or "company" from quickadd dropdown 
		2. *is there a way to use checkbox asking if client is new, if so format differently* #❓

## Person
1. Quickadd macro "Create New Person"
2. Frontmatter fields:
	1. `aliases`
	2. `company`
	3. `location`
	4. `category-person`
	6. `follow-up: false`  
	5. `date-last-spoken`
	6. `birthday`
	7. `email`
3. Meta
	1. `company`  
	2. `Phone`

---
up:: [[Atlas/🧠 Sid\|🧠 Sid]]

