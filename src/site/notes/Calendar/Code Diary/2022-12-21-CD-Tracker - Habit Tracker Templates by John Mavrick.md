---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-21-cd-tracker-habit-tracker-templates-by-john-mavrick/","title":"Habit Tracker Templates by John Mavrick"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> categories:: #log/code 
> language:: [[Sources/Tools + Plugins/Plugin-Tracker\|Plugin-Tracker]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Habit Tracker Templates by John Mavrick
**Language::**  [[Sources/Tools + Plugins/Plugin-Tracker\|Plugin-Tracker]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**::

## Summary
> A bunch of cool templates to track habits using the [[Sources/Tools + Plugins/Plugin-Tracker\|Plugin-Tracker]] plugin

## Code

````Markdown

Status:: 
Tags:: 
Links:: [[🏠 My Home]]
___
# ♻️ My Habits
For [[Creating and tracking your own habits and statistics]]
## Statistics
### Energies
```tracker
searchType: dvField
searchTarget: Physical, Mental, Emotional, Spiritual
folder: /dailyNotes
summary:
    template: "AVERAGES\nPhysical: {{average(dataset(0))}}\nMental: {{average(dataset(1))}}\nEmotional: {{average(dataset(2))}}\nSpiritual: {{average(dataset(3))}}\n"
```
``` tracker
searchType: dvField
searchTarget: Physical, Mental, Emotional, Spiritual
datasetName: Physical, Mental, Emotional, Spiritual
folder: /dailyNotes
month:
    mode: annotation
    startWeekOn: 'Sun'
    threshold: 7, 7, 7, 7
    color: white
    dimNotInMonth: false
    annotation: 💪,🧠,😊,🙏
    showAnnotationOfAllTargets: true
```
## Habits
### Meditation
#### Total
``` tracker
searchType: task.done, task.all
searchTarget: Meditate, Meditate
folder: /dailyNotes
summary:
    template: "Meditate - {{sum(dataset(0))/sum(dataset(1))*100}}% - {{sum(dataset(0))}}/{{sum(dataset(1))}} Days Completed"
```
``` tracker
searchType: task.done, task.notdone
searchTarget: Meditate, Meditate
folder: /dailyNotes
datasetName: Meditate, Not Meditate
month:
    color: green
    todayRingColor: white
    selectedRingColor: steelblue
    showSelectedValue: false
````

___
References:


```

## Explanation

## Result

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]