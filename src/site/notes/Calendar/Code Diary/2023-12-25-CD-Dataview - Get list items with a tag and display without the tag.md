---
{"dg-publish":true,"permalink":"/calendar/code-diary/2023-12-25-cd-dataview-get-list-items-with-a-tag-and-display-without-the-tag/","title":"Get list items with a tag and display without the tag"}
---

> [!metadata]- Meta
> **up**:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> **type**:: #log/code 
> **tags**:: #on/snippets 
> **language**:: [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
> **program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> **topics**:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Get list items with a tag and display without the tag
**Language::**  [[Sources/Tools + Plugins/Plugin - Dataview\|Plugin - Dataview]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**URL**:: [Reddit - Dataview Lines with Tag](https://www.reddit.com/r/ObsidianMD/comments/17s0oiu/dataview_list_of_lines_with_tag/)

## Summary
> Use dataview and regard to get and show items with a tag

## Code

```Dataview

TABLE WITHOUT ID string(link(rows.file.link, rows.title)[0]) AS class, regexreplace(list(rows.L.text), "#exam", "") AS "exam"
FROM "3_semester"
FLATTEN file.lists AS L
WHERE contains(L.tags, "#exam")
GROUP BY file.link
```

## Explanation
I use this snippet to list lines tagged with ‘#exam’ in my folder "3_semester", which I adapted from [this discussion](https://github.com/blacksmithgu/obsidian-dataview/discussions/1329). To show the tag too just remove the regexreplace().

## Result

| class                                                                                       | 🔥                                                                                                                                                                                |
| ------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[Sources/📚 Books/After World\|After World]]                                            | <ul><li><ul><li>These are all amazing, post this some time </li></ul></li></ul>                                                                                                   |
| [[Sources/📚 Books/Blindsight\|Blindsight]]                                              | <ul><li><ul><li>Awesome passage on [[Cards/600 - Applied Sciences/Technology/Technology\|Technology]] </li><li>This seems like the thesis to the entire book here, a lot of ideas baked into this passage, damn! </li></ul></li></ul> |
| [[Sources/📚 Books/Blood Meridian\|Blood Meridian]]                                      | <ul><li><ul><li></li></ul></li></ul>                                                                                                                                              |
| [[Sources/📚 Books/Plato Complete Works\|Plato Complete Works]]                          | <ul><li><ul><li></li></ul></li></ul>                                                                                                                                              |
| [[Sources/📚 Books/The Lathe of Heaven\|The Lathe of Heaven]]                            | <ul><li><ul><li> Lacanian void, objet a</li></ul></li></ul>                                                                                                                       |
| [[Sources/📚 Books/V.\|V.]]                                                              | <ul><li><ul><li>V.'s love for peregrinations throughout an inanimate world until now. Tourism </li></ul></li></ul>                                                                |
| [[Sources/📰 Articles/Fiction and the Figures of Life\|Fiction and the Figures of Life]] | <ul><li><ul><li>Beautiful. </li></ul></li></ul>                                                                                                                                   |

{ .block-language-dataview}

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]