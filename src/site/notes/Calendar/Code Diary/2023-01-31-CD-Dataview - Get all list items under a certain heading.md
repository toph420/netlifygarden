---
{"dg-publish":true,"permalink":"/calendar/code-diary/2023-01-31-cd-dataview-get-all-list-items-under-a-certain-heading/","title":"Get all list items under a certain heading"}
---

> [!metadata]- Meta
> **up**:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> **type**:: #log/code 
> **tags**:: #on/snippets #to/implement 
> **language**:: [[Dataview\|Dataview]]
> **program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> **topics**:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Get all list items under a certain heading
**Language::**  [[Dataview\|Dataview]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**:: [Reddit](https://www.reddit.com/r/ObsidianMD/comments/w9bu1r/query_and_filter_items_under_a_heading/?utm_source=share&utm_medium=ios_app&utm_name=iossmf)

## Summary
> Great discussion about querying specific parts of notes, ie list items under a certain heading 

## Code

> [!summary] Reddit Post
> Query and filter items under a heading
> 
> I have many files with a reference heading in them, like this:
> 
>     # Algorithms
>     
>     Aliquam erat volutpat.  Nunc eleifend leo vitae magna.  In id erat non orci commodo lobortis.  Proin neque massa, cursus ut, gravida ut, lobortis eget, lacus
>     ## References
>     
>     - Author 1: Book 1.
>     - Author 2: Book 2.
>     
> 
> Now I'd like to use a query that collects all those list items under the references heading from across the files and shows them in one view with filename and references.
> 
> So how can I filter results under a heading?
> 
> ---
> 
> You can extract all bullets points under a heading in dataview using something like:
> 
> ```
> TABLE bullet.text AS References
> FROM #TagOfInterest
> FLATTEN file.lists as bullet
> WHERE meta(bullet.section).subpath = "References"
> ```
> 
> You just need to replace the FROM clause with whatever filter will narrow down to just the notes you're interested in (specific tags, folders, links, etc).
> 
> Do you know if / how I can group the results, for instance by filename?
> 
> `Group by file.name` should work, did you get an error or just no results? Once you group, you would also need to change the first line to:
> 
> ```
> TABLE rows.bullet.text
> ```
> 
> The reason is that once you group, you don't have a set of pages anymore - you have key (the value you grouped by), and rows (the set of pages that go with that group).
> 
> That just means you need to put `rows.` in front of things to get to the grouped page info.
> 
> That worked! Thank you very much! Here's the full query:
> 
> ````
>  | file.name | References |
> | --------- | ---------- |
> 
{ .block-language-dataview}
> ````
> 
> What does not work is the sorting. It won't sort by file-names descending.
> 
> Plus, the group-name is vertically centered, instead of aligned to the top of the cell. That makes it hard to read the results table.
> 
> Your sort should work... so I'm surprised it doesn't. Perhaps the group is interfering, so try putting it after the group like `SORT key desc`.
> 
> I also don't like how the group heading are always centered, but I'm not sure how to change it. Maybe there's a css way, but I haven't gone looking. I'll often switch to a LIST instead of a TABLE if I'm grouping because it usually looks better. You have to drop the `AS "References"`if you do that because there are no column headings in a list.
> 
> A last resort is to switch into full JavaScript and manually interfere with the table design... but that's a real step up in complexity - so not for the feint hearted, and not easy to explain over reddit comments 😉
> 
> Wow, that worked like a charm! Here's what the query looks like:
> 
> ````
>  
{ .block-language-dataview}
> ````
> 
> Your help is very much appreciated.
> 
> Sorting does not work, no matter what I write and where I put it (above or below "GROUP BY"). Even "SORT blablaxyz desc" will not be lamented.
> 
> And I think I have to deep dive into "dataviewjs" soon :)
> 
> Weird - I tried your query on my system, sort doesn't work above the group (which must re-sort them asc)... but it works fine below:
> 
> ```
> LIST rows.bullets.text
> FROM "0-0 Inbox"
> FLATTEN file.lists as bullets
> WHERE meta(bullets.section).subpath = "testing"
> GROUP BY file.name
> SORT key desc
> ```
> 
> This is awesome! Thank you. Do you know why it doesn't create links to the files?
> 
> You'd have to group by file.link - instead of just the file.name - but then it should give the links.

## Explanation

## Result

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]