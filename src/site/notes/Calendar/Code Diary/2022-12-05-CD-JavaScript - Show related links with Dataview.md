---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-05-cd-java-script-show-related-links-with-dataview/","title":"Show related links with Dataview"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> type:: #log/code 
> language:: [[Sources/Tools + Plugins/SQL\|SQL]], [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Show related links with Dataview
**Language**::  [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]

## Summary
> Multiple ways to show related links

## Code
**Unrequited Notes (links in but not out)**

```sql
dataview
table file.mtime.year + "-" + file.mtime.month + "-" + file.mtime.day as Modified
from [[My Code Snippets]]
and !outgoing([[My Code Snippets]])
sort file.mtime desc
```

```datavie
Table
from [[AI Art Debate]]
and !outgoing([[AI Art Debate]])
sort file.mtime desc
```

**Related Unlinked Notes**

```sql
dataview
LIST
FROM ""
FLATTEN topics as flattenedTopics
WHERE contains(this.topics, flattenedTopics)
AND file.name != this.file.name AND !contains(this.file.outlinks, file.link)
```

**Unlinked Notes**

```sql
dataview 
Table FROM [[#]] where !contains(this.file.outlinks, file.link) and !contains(topics, this.file.link)
```

**Show tags and tagged notes**

```sql
dataview
TABLE WITHOUT ID (tag + "(" + length(rows.file.link) + ")") AS Tags, join(rows.file.link, ", ") AS Files
WHERE file.tags 
FLATTEN file.tags AS tag
WHERE contains(tag, "source/")
GROUP BY tag 
SORT rows.tag ASC
```

**These notes have the tag `#` and are not mentioned above.**

```sql
dataview
table file.mtime.year + "-" + file.mtime.month + "-" + file.mtime.day as Modified
from #note  
and !outgoing([[My Queries and Code]])
sort file.mtime desc
```

## Explanation
- 

## Result

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]