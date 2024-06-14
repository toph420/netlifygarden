---
{"dg-publish":true,"permalink":"/atlas/icebox/"}
---

>[!metadata]- Meta
>up:: [[🏠 Home\|🏠 Home]]
>type:: #🗺/view 
>status:: #📝/🌲 

# 🧊 Icebox

> This view looks at the 20 newest notes in my **+ Encounters** folder. Process each note, make connections, add details, move them to the best folder,  and delete everything that no longer sparks ✨. 

``` dataview
TABLE WITHOUT ID
 file.link as "New Notes",
 (date(today) - file.cday).day as "Days Alive"
FROM "+ Encounters" and -#on/readme 
SORT file.cday asc
LIMIT 20
```


---
up:: [[🏠 Home\|🏠 Home]]

