---
{"dg-publish":true,"permalink":"/calendar/code-diary/2023-01-28-cd-quickadd-example-quickadd-select-menu/","title":"Example Quickadd Select Menu"}
---

> [!metadata]- Meta
> **up**:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> **type**:: #log/code 
> **tags**:: #on/snippets 
> **language**:: [[Quickadd\|Quickadd]]
> **program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> **topics**:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Example Quickadd Select Menu
**Language::**  [[Quickadd\|Quickadd]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**::

## Summary
> An example from the Quickadd docs describing an implementation that handles Toggl integration, the menu is what interests me here. 

## Code

```js
const menu = {
    "🧠 Learning & Skill Development": { // Sub-menu for Learning and Skill Development
        togglProjectName: "Learning & Skill Development", // Name of your corresponding Toggl project
        menuOptions: {
            "✍ Note Making": "Note Making", // Preset time entry. The left part is what's displayed, and the right part is what Toggl gets.
            "🃏 Spaced Repetition": "Spaced Repetition", // So for this one, I would see '🃏 Spaced Repetition' in my menu, but Toggl would receive 'Spaced Repetition' as the entry.
            "📖 Read Later Processing": "Read Later Processing",
            "👨‍💻 Computer Science & Software Engineering": "Computer Science & Software Engineering",
        }
    },
    "🤴 Personal": {
        togglProjectName: "Personal",
        menuOptions: {
            "🏋️‍♂️ Exercise": "Exercise",
            "🧹 Chores": "Chores",
            "👨‍🔬 Systems Work": "Systems Work",
            "🌀 Weekly Review": "Weekly Review",
            "📆 Monthly Review": "Monthly Review",
            "✔ Planning": "Planning",
        }
    },
    "👨‍🎓 School": {
        togglProjectName: "School",
        menuOptions: {
            "🧠 Machine Intelligence (MI)": "Machine Intelligence (MI)",
            "💾 Database Systems (DBS)": "Database Systems (DBS)",
            "🏃‍♂ Agile Software Engineering (ASE)": "Agile Software Engineering (ASE)",
            "💻 P5": "P5",
        }
    }
};
```

## Explanation

## Result

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]