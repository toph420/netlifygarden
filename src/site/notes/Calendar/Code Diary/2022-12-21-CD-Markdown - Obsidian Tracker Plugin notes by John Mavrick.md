---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-21-cd-markdown-obsidian-tracker-plugin-notes-by-john-mavrick/","title":"Obsidian Tracker Plugin notes by John Mavrick"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> categories:: #log/code 
> language:: [[Sources/Tools + Plugins/Markdown\|Markdown]], [[Sources/Tools + Plugins/Plugin-Tracker\|Plugin-Tracker]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Obsidian Tracker Plugin notes by John Mavrick
**Language::**  [[Sources/Tools + Plugins/Markdown\|Markdown]], [[Sources/Tools + Plugins/Plugin-Tracker\|Plugin-Tracker]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**:: [John Mavricks Notes about Obsidian Tracker](https://johnmavrick.notion.site/Creating-and-tracking-your-own-habits-and-statistics-019ae25085744853a6203f06afac2df2)

## Summary
> Taken from John Mavricks notes about using Tracker for habits

## Code

````Markdown
Status:: 
Tags:: 
Links:: [[Obsidian Community Plugins]]
___
# Obsidian Tracker Plugin
## Implementation
[[♻️ My Habits]]
- Calendar overviews
- Lifetime statistics on habits

[[📆 My Periodic Reviews]]
- [[Weekly Review Template]]
	- Line graph and summary details for each statistic
	- Habits are best viewed through the monthly view and would be redundant if put here so I only have them in monthly reviews
- [[Monthly Review Template]]
	- Statistics (energy level) tracking + averages
	- Habits

## Principles
Can download the [github repository](https://github.com/pyrochlore/obsidian-tracker) and open the `/Examples` folder as an Obsidian vault to see examples
- Will have to manually install the tracker plugin though

The tracker plugin lets you visualize metadata and other content of a folder's notes, which is commonly used for daily notes and habits (but can also be used for analyzing other things as well like the time you spend writing each article, keeping track of task completion, etc)
### Changing existing graphs and values
For the most part, you will just need to add new [[Metadata]] fields in your templates (see [[Daily Template#Energies]] as an example, and you will have to adjust all tracker views in templates to look for them as well by changing `searchTarget`

### Essentials
```
startDate: YYYY-MM-DD
endDate: YYYY-MM-DD
```
- For time-bound statistics inside [[📆 My Periodic Reviews]]
	- For [[Monthly Review Template]]
### Line Graph

> [!INFO] Example
> Used in [[Weekly Review Template#Energy]]


Pros
- Identifying patterns in short timeframes

Cons
- Not good for large timeframes, [[#Calendar View]] is better for monthly onwards

``` tracker
searchType: dvField
searchTarget: Physical, Mental, Emotional, Spiritual
folder: /dailyNotes
startDate: 2022-07-04
endDate: 2022-07-10
datasetName: Physical, Mental, Emotional, Spiritual
line:
    title: Energy
    yMax: 10
    yAxisLabel: Phys (R) / Ment (B) Emot (Y) / Spir (G)
    lineColor: red, blue, yellow, green
    showLegend: true
    legendOrientation: vertical
    fillGap: true
```
- `dataSetName` sets the names of the values on the legend

**Explanations**
```
searchType: dvField
- dvField means that the value it is looking for in the note is an in-line metadata field, like Physical:: 9
  
searchTarget: Physical, Mental, Emotional, Spiritual
- the metadata fields you want to display

datasetName: Physical, Mental, Emotional, Spiritual
- The names to be used in the legend at the bottom

line:

	title: Energy
    yMax: 10
    yAxisLabel: Phys (R) / Ment (B) Emot (Y) / Spir (G)
    
    showLegend: true
    legendOrientation: vertical
    - used to show legends
    
    fillGap: true
    - so the lines don't discontinue when you forget to put in values for a day
```
### Calendar View
> [!INFO] Example
> Used in:
> - [[♻️ My Habits]]
> - [[Monthly Review Template#Key Metrics]]


Pros
- To see lots of values at once
- Good for summaries

Cons
- Can't see multiple specific values on a certain day
- Can't put too much on one line
#### Summary
Useful for a quick view on a group of habits or statistics
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
**Explanations**
```
month:
    mode: annotation
    - Allows for the summary view
    startWeekOn: 'Sun'
    threshold: 7, 7, 7, 7
    - Must match or be avbo
    color: white
    dimNotInMonth: false
    annotation: 💪,🧠,😊,🙏
    - set in same order
    showAnnotationOfAllTargets: true
    - set false to be able to toggle between by clicking on the field label at the top
```
#### Single View
``` tracker
searchType: dvField
searchTarget: Physical, Mental, Emotional, Spiritual
datasetName: Physical, Mental, Emotional, Spiritual
folder: /dailyNotes
month:
    startWeekOn: 'Sun'
    threshold: 7, 7, 7, 7
    color: green
    dimNotInMonth: false
    todayRingColor: white
    selectedRingColor: steelblue
    circleColorByValue: true
    showSelectedValue: true
```
- A dot will only be connected if it is past the threshold and the dots it is connecting to are also above. the threshold
- Green is apparently the color with [the most differentiable shades](https://www.quora.com/Why-does-the-human-eye-see-more-shades-of-green-than-any-other-colour), so consider using it
#### Extra Information
`initMonth` to initially set what month
- ex) `initMonth: 2022-09`
### Summary View
> [!INFO] Example
> Used in:
> - [[Weekly Review Template#Energy]]
> - [[Monthly Review Template#Key Metrics]]
> - [[♻️ My Habits]]


Pros
- Easy to glance at and understand

Cons
- Should be supported with another visual graph

#### Summary of Physical Energy
```tracker
searchType: dvField
searchTarget: Physical
folder: /dailyNotes
summary:
    template: "Minimum: {{min()}}\nMaximum: {{max()}}\nMedian: {{median()}}\nAverage: {{average()}}\nSum: {{sum()}}"
```
- Can cut off with specific date ranges as well
- Wrap the variables in `{{}}` tags
#### Combining Multiple Energies
```tracker
searchType: dvField
searchTarget: Physical, Mental, Emotional, Spiritual
folder: /dailyNotes
summary:
    template: "AVERAGES\nPhysical: {{average(dataset(0))}}\nMental: {{average(dataset(1))}}\nEmotional: {{average(dataset(2))}}\nSpiritual: {{average(dataset(3))}}\n"
```
- `dataset(x)` where x is the index of the field in `searchTarget`, starting from 0
- Can perform basic arithmetic using symbols
- Use functions to calculate average-related stuff
### Task View
Pros
- Track basic markdown checkboxes, works with tasks plugin
- If using todoist, can use completed tasks plugin

``` tracker
searchType: task.done, task.all
searchTarget: Read, Read
folder: /dailyNotes
summary:
    template: "Read - {{sum(dataset(0))/sum(dataset(1))*100}}% - {{sum(dataset(0))}}/{{sum(dataset(1))}} Days Completed"
```

Explanations

```
searchType: task.done, task.all
- can also use task.notdone
searchTarget: Read, Read
- Value should be the content on the same line as the task checkbox, which is duplicated since we need both done and all values
folder: /dailyNotes
summary:
    template: "Read - {{sum(dataset(0))/sum(dataset(1))*100}}% - {{sum(dataset(0))}}/{{sum(dataset(1))}} Days Completed"
    - 
```

``` tracker
searchType: task.done, task.notdone
searchTarget: Read, Read
folder: /dailyNotes
datasetName: Read, Not Read
month:
    color: green
    todayRingColor: white
    selectedRingColor: steelblue
    showSelectedValue: false
```

___
References:

Created:: 2022-12-19 11:51
````

## Explanation

## Result

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]