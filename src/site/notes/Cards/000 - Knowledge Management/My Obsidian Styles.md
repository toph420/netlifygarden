---
{"dg-publish":true,"permalink":"/cards/000-knowledge-management/my-obsidian-styles/","title":"My Obsidian Styles"}
---

> [!metadata]- Meta
> **up**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> **type**:: #📝 
> **status**:: #📝/🌞
> **tags**::  
> **topics**:: 
> **links**::


# My Obsidian Styles

> Tracking all the custom styled elements in this vault

- [[Cards/000 - Knowledge Management/Snippet - Capacities Sidebar\|Snippet - Capacities Sidebar]]
## Tables

### Image and Labeled Fields

``` dataview
TABLE WITHOUT ID EmbededCoverImg as "", link(file.link, title) + "<span class='summary'>**Summary:** " + summary + "</span>" + "<span class='summary'>**Prompt:** " + prompt + "</span>" AS Prompts
FROM "Calendar/Prompt Journal"
WHERE !contains(file.path, "Calendar/+ MOCs") & contains(file.name, "20")
FLATTEN choice(typeof(image)="link",
	embed(link(meta(
		choice(
			typeof(image)="link", 
				image, this.file.link
		)
	).path, "200")), "![anyName|200](" + image + ")") AS EmbededCoverImg
SORT file.ctime asc
LIMIT 1
```

> [!code]- Code
> ``` sql
> TABLE WITHOUT ID EmbededCoverImg as "", link(file.link, title) + "<span class='summary'>**Summary:** " + summary + "</span>" + "<span class='summary'>**Prompt:** " + prompt + "</span>" AS Prompts
> FROM "Calendar/Prompt Journal"
> WHERE !contains(file.path, "Calendar/+ MOCs") & contains(file.name, "20")
> FLATTEN choice(typeof(image)="link",
> 	embed(link(meta(
> 		choice(
> 			typeof(image)="link", 
> 				image, this.file.link
> 		)
> 	).path, "200")), "![anyName|200](" + image + ")") AS EmbededCoverImg
> SORT file.ctime asc
> LIMIT 1
> ```

### Simple title, summary, and date

| Entries                                                                                                                     |
| --------------------------------------------------------------------------------------------------------------------------- |
| [[Calendar/Journal/Daily/2024-06-19\|2024-06-19]]<span class='summary'>\-</span><span class='block'>June 19, 2024</span> |

{ .block-language-dataview}

> [!code]- Code
> ```sql
> TABLE WITHOUT ID file.link + "<span class='summary'>" + summary + "</span><span class='block'>" + date(regexreplace(file.name, "^.*(\d\d\d\d-\d\d-\d\d).*$", "$1")) + "</span>" AS Entries
> FROM "Calendar/Journal" and -"Calendar/Journal/delete.md"
> SORT file.ctime desc
> LIMIT 1
> ```

### Regex Date from Title

| Meetings                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [[Calendar/Meetings/2024-05-30-M-GRCF - Video opportunities for GRCF\|Video opportunities for GRCF]]<span class='summary'>Discussing some new potential videos for GRCF, including Annual Report</span><span class='summary'>**Client:** [[Spaces/🦆 Ducks Films/Areas/🤑 Clients/GRCF/GRCF\|Grand Rapids Community Foundation]]</span></span><span class='block'>May 30, 2024 |

{ .block-language-dataview}

> [!code]- Code
> ```sql
> TABLE without id link(file.name, title) + "<span class='summary'>" + summary + "</span><span class='summary'>**Client:** " + client + "</span></span><span class='block'>" + date(regexreplace(file.name, "^.*(\d\d\d\d-\d\d-\d\d).*$", "$1")) as Meetings
> From "Calendar/Meetings"
> SORT file.ctime desc
> Limit 1
> ```


---
up:: [[🏠 Home\|🏠 Home]]

