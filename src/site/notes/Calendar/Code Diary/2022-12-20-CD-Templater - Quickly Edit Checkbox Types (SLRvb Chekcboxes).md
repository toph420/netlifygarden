---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-20-cd-templater-quickly-edit-checkbox-types-sl-rvb-chekcboxes/","title":"Quickly Edit Checkbox Types (SLRvb Checkboxes)"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> type:: #log/code 
> language:: [[Sources/Tools + Plugins/Plugin - Templater\|Plugin - Templater]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Quickly Edit Checkbox Types (SLRvb Checkboxes)
**Language::**  [[Sources/Tools + Plugins/Plugin - Templater\|Plugin - Templater]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**::

## Summary
> Use this script to select and update checkbox types, ie change a regular `- [ ]` into `- [i]` for an "Idea" type. Use hotkey `opt + shift + t` to trigger.opt + shift + t` to trigger.

## Code

```js
<%*
const slrvbCheckboxes = [[
"Unchecked",
"Regular", 
"Checked", 
"Dropped", 
"Forward", 
"Defer", 
"Question", 
"Half Done", 
"Add", 
"Research", 
"Important", 
"Idea", 
"Brainstorm", 
"Pro", 
"Con", 
"Quote", 
"Note", 
"Bookmark", 
"Information"
], [
" ",
"x", 
"X", 
"-", 
">", 
"D", 
"?", 
"/", 
"+", 
"R", 
"!", 
"i", 
"B", 
"P", 
"C", 
"Q", 
"N", 
"b", 
"I"
]];

const sanctumCheckboxes = [[
"Unchecked",
"Star",
"Alarm / Reminder / Notification",
"Favourite",
"Savings / Piggy bank",
"Savings alternative / Piggy bank",
"Cancelled",
"Rescheduled / Forwarded",
"Scheduled",
"Location",
"Bug / Debug",
"Failure",
"Note / Annotation",
"Pros",
"Cons",
"Win / Success / Reward",
"Bookmark / References",
"Idea / Tip",
"Important / Attention",
"Question / Cue",
"Info"
], [
" ",
"⭐",
"a",
"❤",
"s",
"S",
"-",
">",
"<",
"l",
"B",
"X",
"n",
"p",
"c",
"W",
"b",
"I",
"!",
"?",
"i"
]];

const selection = tp.file.selection();
const checkboxType = slrvbCheckboxes; //Change this
const check = await tp.system.suggester(checkboxType[0], checkboxType[1], true);

//Check Replacement
if (selection) {
    const replace = selection.split("\n").map(select => {
    if (select.match(/- \[.\]/)) {
        select = select.replace(/\[.\]/, `[${check}]`);
    }
    return select;
    }).join("\n");
    tR += replace;
} else {
    new Notice("Text must be selected");
};

%>
```

## Explanation
1. Select a line if a task
2. I use a hotkey to trigger the template [[Extras/Templates/Functions/Task Changer\|Task Changer]] with it selected 

### Additionally
Use this code to get these custom checkboxes 

```datavie
TASK 
FROM #log  
WHERE contains(status, "i")
```


## Result

![[Obsidian_NVA9eSfNIr.gif\|Obsidian_NVA9eSfNIr.gif]]
![[Obsidian_GRw3CAvq99.gif\|Obsidian_GRw3CAvq99.gif]]---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]