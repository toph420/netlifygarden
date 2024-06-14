---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-04-cd-java-script-quickadd-api-multi-select/","title":"Quickadd API Multi Select"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> type:: #log/code 
> language:: [[Sources/Tools + Plugins/JavaScript\|JavaScript]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]], [[Sources/Tools + Plugins/Plugin - Quickadd\|Quickadd]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]
---

# Quickadd API Multi Select

## Summary
> Put this in your capture for a multi select 

## Code
```JavaScript
const suggester = this.quickAddApi.suggester;
let toSuggest = ["Up late", "Fast asleep", "Poor sleep", "Done"];
const responses = [];
let response;

while (response !== "Done") {
    response = await suggester(toSuggest, toSuggest);
    if (response !== "Done") {
        responses.push(response);
        toSuggest = toSuggest.map(s => s === response ? `✅ ${s}` : s);
    }
}

return responses.join(", ");
```

## Explanation
- 

## Result


---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]