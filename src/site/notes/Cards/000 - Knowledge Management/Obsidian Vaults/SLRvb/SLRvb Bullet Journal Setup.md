---
{"dg-publish":true,"permalink":"/cards/000-knowledge-management/obsidian-vaults/sl-rvb/sl-rvb-bullet-journal-setup/","title":"SLRvb Bullet Journal Setup"}
---


# SLRvb Bullet Journal Setup

> [!multi-column]
> 
>> [!metadata]- Meta
>> **up**:: [[Atlas/📥 Sources\|📥 Sources]]
>> **type**:: #📥/🔗 
>> **status**:: #📥/🟥 
>> **tags**:: 
>
>> [!ABSTRACT]- Article Info
>> **Author**: 
>> **Title**: SLRvb Bullet Journal Setup
>> **URL**: [Link](https://publish.obsidian.md/slrvb/90+Site/Nebula/N_W+Bullet+Journal+Setup)

> ## Bullet Journal
> 
> > How I personally go about journaling the things that happen in my life.
> 
> ![Setup-Journal.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal.png)
> 
> ## Resources
> 
> **CSS:**
> 
> -   [ITS Theme](https://forum.obsidian.md/t/theme-its-dark-light-theme) (Also available on the Community Themes)
> -   [All Alternate Themes CSS Snippet](https://github.com/SlRvb/Obsidian--ITS-Theme/blob/main/Theme%20-%20All%20Alternate%20Themes.css) (SlRvb Gray toggled on using Style Settings)
> -   [Folder Styles CSS Snippet](https://github.com/SlRvb/Obsidian--ITS-Theme/blob/main/S%20-%20Folder%20Styles.css)
> 
> **Plugins:**
> 
> -   Dataview
> -   Templater
> -   QuickAdd
> 
> # Folder Setup
> 
> I had a couple areas of my life that I wanted to track which now are the folders you see in the screenshot above.
> 
> The reason the folders are separated is just _for me_ to easily search through the folders to find which kind of journal entry I'm looking for on what day.
> 
> I'm using numbers at the beginning of the folder names just to sort them in the order I want to see the folders in, they don't really mean anything beyond that.
> 
> ![[Screen Shot 2022-12-02 at 3.38.34 PM.png\|Screen Shot 2022-12-02 at 3.38.34 PM.png]]
> 
> # 0 BuJo: MOCs
> 
> Most of the MOC pages heavily utilize Dataview to list out the entries dynamically so that I don't have to spend time linking things myself.
> 
> > The fields these dataview tables use are in the **[Journal Sections](https://publish.obsidian.md/slrvb/90+Site/Nebula/N_W+Bullet+Journal+Setup#Journal%20Sections)**.
> 
> ## Journal Homepage
> 
> ````md
> ---
> tags: Journal, MOC/HQ
> cssclass: hcl, readable
> 
> JD: 10
> Order: 0
> 
> Description: "Record of the times."
> ---
> 
> # Journal
> > ` dv= this.Description`
> 
> ###### Currently
>  | Entries |
> | ------- |
> 
{ .block-language-dataview}
> 
> ---
> 
> ![[10 BuJo/1 Journal/2021/2021|no-title]]
> 
> ###### Areas
> [[Timeline]]
> [[Dream Journal]]
> [[Workout]]
> [[Code Diary]]
> [[Resonance Calendar]]
> [[Conditions Log]]
> ````
> 
> **Result:**  
> ![Setup-Journal - Homepage.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal%20-%20Homepage.png)
> 
> ## Timeline
> 
> > Timeline page was inspired by this [**Timeline - § Sim Salis - Obsidian Publish**](https://publish.obsidian.md/sim/Timeline), but it's now a defunct link unfortunately.
> 
> I just use it to list out what notable events happened in each year and if I _have_ a year page, I'll link to it. I think it's just a neat way to see your life at a glance and all the things you've been able to do.
> 
> ```md
> Year | Notable Events |
> -----|----------------|
> `YYYY` | Comma separated list of notable events
> `[[2021]]` | Created ITS Theme, Obsidian Community Showcase
> ```
> 
> ## Dream Journal
> 
> ````sql
>  | Dream | Date |
> | ----- | ---- |
> 
{ .block-language-dataview}
> ````
> 
> ## Workout Log
> 
> ````sql
>  | Entry | Type______ | Challenge__ | Notes |
> | ----- | ---------- | ----------- | ----- |
> 
{ .block-language-dataview}
> ````
> 
> **Result:**  
> ![Setup-Journal - Workout DV.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal%20-%20Workout%20DV.png)
> 
> ## Conditions Log
> 
> There was a lot of information on these pages, so I opted to get very CSS heavy on the dataview query so that I could still glance and get the information I needed.
> 
> ````sql
>  | Entry | Information___________ | Note |
> | ----- | ---------------------- | ---- |
> 
{ .block-language-dataview}
> ````
> 
> **Result:**  
> ![Setup-Journal - Conditions Log DV.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal%20-%20Conditions%20Log%20DV.png)
> 
> ## Code Diary
> 
> ````sql
>  | Entry |
> | ----- |
> 
{ .block-language-dataview}
> ````
> 
> **Result:**  
> ![Setup-Journal - Code Diary DV.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal%20-%20Code%20Diary%20DV.png)
> 
> ## Resonance Calendar
> 
> ````sql
> ##### In Progress
>  | Entry | Date |
> | ----- | ---- |
> 
{ .block-language-dataview}
> 
> ###### Mobile
>  | ENTRY |
> | ----- |
> 
{ .block-language-dataview}
> ````
> 
> **Result:**  
> ![Setup-Journal - Resonance Calendar DV.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal%20-%20Resonance%20Calendar%20DV.png)
> 
> ## Update Log
> 
> ````sql
>  | Entry | Updated_______ |
> | ----- | -------------- |
> 
{ .block-language-dataview}
> ````
> 
> **Result:**  
> ![Setup-Journal - Update Log DV.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal%20-%20Update%20Log%20DV.png)
> 
> # Journal Sections
> 
> The naming scheme of my files is something new and was done to help me quickly identify what type of entry it is. My old system just had the date then a title, but when listing or searching through them it was hard to tell what kind I was looking at. So I came up with this:
> 
> **File Title Format**: `YYYY-MM-DD-JT-ST - Title`
> 
> -   `JT` being the initials for the `Journal Type`
> -   `ST` being intials for the `subtype` of the Journal Type
> 
> Initials
> 
> Type
> 
> `J`
> 
> Journal Day
> 
> `DJ`
> 
> Dream Journal
> 
> `WL`
> 
> Workout Log
> 
> `WL-A`
> 
> Workout Log Arm Day
> 
> `WL-T`
> 
> Workout Log Torso Day
> 
> `WL-L`
> 
> Workout Log Lower Body Day
> 
> `CD`
> 
> Code Diary
> 
> `UL`
> 
> Update Log
> 
> `R`
> 
> Resonance Calendar
> 
> `CL`
> 
> Conditions Log
> 
> **Examples:**
> 
> -   `2021-07-24-J - Community Showcase`
> -   `2021-07-27-DJ - The Dream`
> -   `2021-06-19-WL-L - New Leg Routine`
> 
> ## 1 Journal
> 
> #### Daily Journal Entry
> 
> My journal entries for daily notes are often very bare bones, because if I tried to record too much in/about a day I would _never_ write anything. It's been a struggle to find out what it would take to get me to write regularly, but I think this template/setup is the closest I can get to nearly daily writing.
> 
> ---
> 
> The **File Title** often is a couple words about each important event that day; sometimes it's only 1 event and sometimes it's 3+. If there's more than 1, I'll just add a `+` plus sign between the titles to help me see the separation.  
> **Example**: `2021-05-11-J - Dying Internet + CSV to MD Fixes`
> 
> ```md
> ---
> tags: Journal/Date/Day
> 
> Date: <% tp.file.title.split("-J ")[0] %>
> Title: <% tp.file.title.split(" - ")[1] %>
> ---
> <i>**[[Journal]]**, [[Day]]</i>
> 
> # <% moment(tp.file.title.split("-J")[0]).format("dddd DD, MMMM YYYY") %>
> **Year**:: [[<% moment(tp.file.title.split("-J")[0]).format("YYYY") %>]]
> **Month**:: [[<% moment(tp.file.title.split("-J")[0]).format("YYYY-MM") %>]]
> **Rating**:: [[Rating]]
> **Tags**:: 
> 
> ---
> # Summary
> - <% tp.file.cursor(2) %>
> 
> ---
> 
> ## Event Title
> - Event
> 
> ```
> 
> The **Summary section** is to finally get me to at least put a brief version of the important events that happened that day.
> 
> The **Event Title** headings after that are for more indepth recounts of the events of that day if it's really notable for me. Everything else regarding the actual events is written in bullet points because I do not want to write more than I have to and bullets are just far easier for me to reread.
> 
> #### Yearly Journal Entry
> 
> The yearly journal entry note is also bare bones as well, if not moreso.
> 
> The **File Title** is just the year number (ie. `2021`).
> 
> ````md
> ---
> tags: Journal/Date/Year
> 
> Date: <% tp.file.title %>
> ---
> <i>[[Journal]], [[Year]]</i>
> 
> # <% tp.file.title %>
> **Rating**::
> **Tags**::
> 
> ---
> 
> # Theme: 
> - [ ] 
> 
> 
> ---
> # Reflections
> - 
> 
> ---
> # Entries
>  
{ .block-language-dataview}
> ````
> 
> Inspired by the video: [**Your Theme** by CGP Grey](https://youtu.be/NVGuFdX5guE), I have a section for what my theme is for the year. Under that heading is just a place for some task that I might want to accomplish, but sometimes I just delete that and go straight for the reflections.
> 
> **Reflections** are something that I fill out throughout the year, because I definitely won't remember nor will I want to sit down at the end of the year and try to remember everything that occurred. By the end of the year I want to _read_ what I accomplished.
> 
> The **Entries** section is just a large list of all the files with the year that matches the current notes year.
> 
> ## 2 Dream Journal
> 
> The dream note is far more free form and actually written in paragraphs. Most of the time it's often done _right_ when I wake up if I can remember the dream.
> 
> ```md
> ---
> tags: Journal/Dream
> 
> Date: <% tp.file.title.split("-DJ")[0] %>
> Title: <% tp.file.title.split(" - ")[1] %>
> ---
> <i>**[[Dream Journal]]**, [[Journal]]</i>
> 
> # <% moment(tp.file.title.split("-DJ")[0]).format("dddd DD, MMMM YYYY") %>
> **Year**:: [[<% moment(tp.file.title.split("-DJ")[0]).format("YYYY") %>]]
> **Month**:: [[<% moment(tp.file.title.split("-DJ")[0]).format("YYYY-MM") %>]], <% tp.date.now("MMMM") %>
> **Tags**::
> **Fandom**:: 
> **People**:: 
> 
> ---
> # Event Of Dream
> 
> ```
> 
> ![Setup-Journal - Dream Journal Page.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal%20-%20Dream%20Journal%20Page.png)
> 
> ## 3 Workout Log
> 
> > The workout log is where I record my reps of my workout routine to measure my progress.
> 
> The workout log isn’t anything fancy, I just have a Form section on the table where I note how I felt for that particular exercise. Since there are a _couple_ of templates for this part of the journal, I’ll show the results first so you understand what all these pages end up looking like since they’re all the same.
> 
> ![Setup-Journal - Workout Log Page.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal%20-%20Workout%20Log%20Page.png)
> 
> **Arm Day Template**
> 
> ```md
> ---
> tags: Journal/Workout/Arms
> cssclass: table, t-c, writing
> ---
> %%
> Date:: <% tp.file.title.split(/-WL-/)[0] %>
> Year:: [[<% moment(tp.file.title.split(/-WL-/)[0]).format("YYYY") %>]]
> Month:: [[<% moment(tp.file.title.split(/-WL-/)[0]).format("YYYY-MM") %>]]
> 
> Workout:: [[Intense 5 Min Workouts -- Anabolic Aliens#Arms]]
> Area:: Arms
> Weight:: 
> Intensity::
> 
> Title::<% tp.file.title.split(" - ")[1] %>
> Notes:: 
> %%
> 
> <i>**[[Workout]]: ` dv= this.Area`**, [[Journal]]
> ` dv= this.Workout`
> </i>
> 
> # <% moment(tp.file.title.split(/-WL-/)[0]).format("dddd DD, MMMM YYYY") %>
> > ` dv= this.Notes`
> 
> Exercise | Time | Log |
> ---------|:----:|-----|
> **TRICEPS**||
> [[Overhead Extension]] | 1 Min |
> [[1-Arm Landmine Extension]] | L: 30 sec<br>R: 30 sec |
> [[1-Arm Landmine Kickback]] |  L: 30 sec<br>R: 30 sec |
> [[Skullcrushers]] | 1 Min |
> [[Close-Grip Bench Press]] | 1 Min | 
> ||
> **BICEPS** ||
> [[Bicep Curl]]| 1 Min |
> [[Reverse Curl]]| 1 Min |
> [[Drag Curl]]| 1 Min |
> [[Cross Arm Landmine Curl]]| L: 30 sec<br>R: 30 sec |
> [[Concetration Landmine Curl]]| L: 30 sec<br>R: 30 sec |
> ||
> **FOREARMS**||
> [[Reverse Wrist Curl]] | 1 Min |
> [[Rotated Wrist Curl]] | 1 Min |
> [[Foreward Roll]] | 1 Min |
> [[Reverse Roll]] | 1 Min |
> [[Landmine Swing Backs]] | L: 30 sec<br>R: 30 sec |
> 
> ## Vids
> 
> <iframe width="100%" height="315" src="https://www.youtube.com/embed/R4xRByps7nY" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
> 
> <iframe width="100%" height="315" src="https://www.youtube.com/embed/U9sdYBBs1rc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
> 
> <iframe width="100%" height="315" src="https://www.youtube.com/embed/Nhqo1oLoMCc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
> ```
> 
> **Torso Day Template**
> 
> ```md
> ---
> tags: Journal/Workout/Torso
> cssclass: table, t-c, writing
> ---
> %%
> Date:: <% tp.file.title.split(/-[A-Z]-/)[0] %>
> Year:: [[<% moment(tp.file.title.split(/-[A-Z]-/)[0]).format("YYYY") %>]]
> Month:: [[<% moment(tp.file.title.split(/-[A-Z]-/)[0]).format("YYYY-MM") %>]]
> 
> Workout:: [[Intense 5 Min Workouts -- Anabolic Aliens#Torso]]
> Area:: Torso
> Weight:: 
> Intensity:: 
> 
> Title::<% tp.file.title.split(/-[A-Z]-/)[1] %>
> Notes:: 
> %%
> 
> <i>**[[Workout]]: ` dv= this.Area`**, [[Journal]]
> ` dv= this.Workout`
> </i>
> 
> # <% moment(tp.file.title.split(/-[A-Z]-/)[0]).format("dddd DD, MMMM YYYY") %>
> > ` dv= this.Notes`
> 
> Exercise | Time | Log |
> ---------|:----:|-----|
> **CHEST** |
> [[Standard Alternating Fly]] | 1 Min |
> [[Standing Alternate Press]] | 1 Min |
> [[Standing Upward Fly]] | R: 30 Sec<br>L: 30 Sec |
> [[Standing Landmine Press]] | 1 Min | 
> [[Wide-Grip Floor Press]] | 1 Min |
> **BACK** |
> [[T-Rows]] | 1 Min |
> [[1-Arm Landmine Row]] | R: 30 Sec<br>L: 30 Sec |
> [[Front Shrug]] | 1 Min | 
> [[Underhand Row]] | 1 Min |
> [[Good Morning]] | 1 Min |
> **SHOULDERS** |
> [[Front Raise]] | 1 Min |
> [[Overhead Press]] | 1 Min | 
> [[Landmine Face Pull]] | 1 Min |
> [[Landmine Bent Arm Side Raise]] | R: 30 Sec<br>L: 30 Sec |
> [[Over Behind]] | 1 Min | 
> 
> # Vids
> ![[Intense 5 Min Workouts -- Anabolic Aliens#Torso]]
> ```
> 
> **Lower Body Day Template**
> 
> ```md
> ---
> tags: Journal/Workout/Leg, Journal/Workout/Core
> cssclass: table, t-c, writing
> ---
> %%
> Date:: <% tp.file.title.split(/-[A-Z]-/)[0] %>
> Year:: [[<% moment(tp.file.title.split(/-[A-Z]-/)[0]).format("YYYY") %>]]
> Month:: [[<% moment(tp.file.title.split(/-[A-Z]-/)[0]).format("YYYY-MM") %>]]
> 
> Workout:: [[Intense 5 Min Workouts -- Anabolic Aliens#Lower Body]]
> Area:: Legs, Abs
> Weight:: 
> Intensity:: 
> 
> Title::<% tp.file.title.split(/-[A-Z]-/)[1] %>
> Notes:: 
> %%
> 
> <i>**[[Workout]]: ` dv= this.Area`**, [[Journal]]
> ` dv= this.Workout`
> </i>
> 
> # <% moment(tp.file.title.split(/-[A-Z]-/)[0]).format("dddd DD, MMMM YYYY") %>
> > ` dv= this.Notes`
> 
> Exercise | Time | Rest | Form |
> ---------|:----:|:----:|------|
> **Leg** |
> [[Jump Squat]] | 45 sec | 15 sec | 
> [[Alternating Stepping Lunge]] | 45 sec | 15 sec | 
> [[Single-Leg Hip Thrust]] | L: 45 sec<br>R: 45 sec | 15 sec | 
> [[Alternating Stiff-Leg Deadlift]] | 45 sec | 15 sec | 
> [[Standing Calf Raise]] | 45 sec | 15 sec | 
> [[Speed Air Squat]] | 45 sec | 15 sec | 
> [[Alternating Side-Lunge]] | 45 sec | 15 sec | 
> [[Hamstring Heel Curl]] | 45 sec | 15 sec | 
> [[Static Squat Hold]] | 45 sec | 15 sec | 
> **Core** |
> [[Rising Flutters]] | 30 sec ||
> [[Rocker]] | 30 sec ||
> [[Toe Touchers]] | 30 sec ||
> [[Penguins]] | 30 sec ||
> [[Legs Extended Crunches]] | 30 sec ||
> [[Touch & Go's]] | 30 sec ||
> [[Hip Thrusts]] | 30 sec ||
> [[Bikes]] | 30 sec ||
> [[Leg Crunches]] | 30 sec ||
> [[Busters]] | 30 sec ||
> 
> 
> # Vids
> [Intense 10 Min Full Lower Body "At Home Workout"](https://youtu.be/erKJOb51bCI)
> <iframe width="100%" height="315" src="https://www.youtube.com/embed/erKJOb51bCI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
> 
> 
> [Intense 5 Minute Ab Workout](https://www.youtube.com/watch?v=ITPcN8U_tYg)
> <iframe width="100%" height="315" src="https://www.youtube.com/embed/ITPcN8U_tYg" frameborder="0" 
> ```
> 
> ## 4 Conditions Log
> 
> The conditions log entry is _very_ new in my system. It used to be a lot random notes with 0 structure to them, but I finally came up with fields that I actually can fill out that are very helpful. I just tried to remember a specific event and what kind of information I wanted to know about, and these were the ones I wanted to have answers for.
> 
> **Template**
> 
> ```md
> ---
> tags: Journal/Condition
> cssclass: table, t-c, hcl
> 
> Date: <% tp.file.title.split("-CL ")[0] %>
> Title: <% tp.file.title.split(" - ")[1] %>
> 
> Event: 
> Start: 
> End: 
> 
> Symptom: 
> Area: 
> Cause: 
> Condition: 
> 
> Pain: 
> Distress: 
> ---
> %%
> Note::
> 
> Year:: [[<% moment(tp.file.title.split("-CL")[0]).format("YYYY") %>]]
> Month:: [[<% moment(tp.file.title.split("-CL")[0]).format("YYYY-MM") %>]]
> %%
> <i>**[[Conditions Log]]**, [[Journal]]</i>
> 
> 
> # <% moment(tp.file.title.split("-CL")[0]).format("dddd DD, MMMM YYYY") %>
> 
> ||
> ---|---|
> Start | ` dv= this.Start`
> End | ` dv= this.End`
> Event | ` dv= this.Event`
> Symptom | ` dv= this.Symptom`
> Area | ` dv= this.Area`
> Cause | ` dv= this.Cause`
> Condition | ` dv= this.Condition`
> Pain | ` dv= this.Pain`
> Distress | ` dv= this.Distress`
> 
> <b> ` dv= this.Note` </b>
> 
> ###### Summary
> - 
> ```
> 
> **Result:**  
> ![Setup-Journal - Condition Page.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal%20-%20Condition%20Page.png)
> 
> ## 5 Code Diary
> 
> > Inspired by this video: [**Code Diary: How and Why to Keep One** by Semicolon&Sons](https://www.youtube.com/watch?v=tarmCEHfGa0), I decided to create a code diary.
> 
> That video breaks down why to use and what goes into a code diary far more than I will, so do watch the video if you're interested.
> 
> For my personal Code Diary so far, I mostly write down code that, through trial and error, I came up with that does a particular thing that may be useful to know why it was done or just _what_ it does.
> 
> **Template:**
> 
> ````md
> ---
> tags: Journal/Code-Diary
> 
> Date: <% tp.file.title.split("-CD")[0] %>
> Title: <% tp.file.title.split(" - ")[1] %>
> ---
> <i>**[[Code Diary]]**, [[Journal]]
> [[Coding-<% tp.file.cursor(1) %>|<% tp.file.cursor(2) %>]], [[Program-<% tp.file.cursor(3) %>|<% tp.file.cursor(4) %>]]
> </i>
> 
> # Code
> ```<% tp.file.cursor(5) %>
> ```
> 
> # Explanation
> - <% tp.file.cursor(6) %>
> 
> # Result
> 
> ````
> 
> **Result:**  
> ![Setup-Journal - Code Diary Page.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal%20-%20Code%20Diary%20Page.png)
> 
> ## 6 Resonance Calendar
> 
> > I was inspired by this video [**How I use Notion as a Resonance Calendar** by Ali Abdaal](https://www.youtube.com/watch?v=lKYBB-Uw1IM), watch through the video for a more indepth look at what a Resonance Calendar is.
> 
> The resonance calendar is a journal entry about a work challenges the way I think or provides new insights.
> 
> ---
> 
> The **File Title** format: `YYYY-MM-DD-R - Title -- Creator`.  
> The double dashes to me signify that it's a work with a creator that isn't me. Anything that comes after `--` tells me _that's_ the creator. Usually I would have these flipped, but the work title is slightly more important to me to see first.
> 
> **Template:**
> 
> ```md
> ---
> tags: Journal/Resonance
> cssclass: hcl
> Date: <% tp.file.title.split("-R")[0] %>
> ---
> %%
> Title:: <% tp.file.title.split(" - ")[1].replace(/ --.\*/, '') %>
> Creator:: <% tp.file.title.split(" -- ")[1] %>
> Source:: <% tp.file.cursor(1) %>
> Media:: [[Medium]]
> %%
> <i>**[[Resonance Calendar]]**</i>
> 
> # <% tp.file.title.split("-R")[1].replace(/ --.*/, '') %>
> <i>`dv= this.Source`</i>
> 
> <iframe width=100% height=300px src="<% tp.file.cursor(2) %>" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
> 
> # Notes
> <% tp.file.cursor(3) %>
> ```
> 
> The page has some **metadata** about the work that I want to know:
> 
> -   The **Date** when I decided to add it to the journal
> -   Who the **Creator** of that work is
> -   The **Source**/where I found it
> -   What type of **Media** it is (ie. Video, Podcast, Article, Book, etc)
> 
> Then I'll embed that source if I can, otherwise I'll just delete the `iframe` and continue onto my notes.
> 
> The notes aren't anything special, this is still a fairly new setup for me, so it's just bullet points on things I found interesting or profound from the work.
> 
> If I haven't finished taking notes on the video I'll just randomly throw in a tag so that it looks ugly and bothers me so I _have_ to go through the video to get rid of it. Which is nice because I can have my mind blown all over again.
> 
> **Result:**  
> ![Setup-Journal - Resonance Calendar Page.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal%20-%20Resonance%20Calendar%20Page.png)
> 
> ## 7 Update Log
> 
> > The **Update Log** is where I list out the things I've changed between creation or the last update of a project.
> 
> I keep the update log's page very simple as it's just the bare bones outline of the updates I've added. For now, the only project that I have that I need updates for is the [**ITS Theme**](https://forum.obsidian.md/t/theme-its-dark-light-theme).
> 
> The title and date are usually left blank until I feel I've done enough to finally push an update through. _Then_, I'll add the information manually to all of it. The only thing that’s updated first is the Project wikilink.
> 
> ---
> 
> The **File Title** will be formatted `YYYY-MM-DD-UL-PI - Updates`. `PI` is the project initials that I decide on, usually about 2-5 letters depending on the title. **For example**, for the ITS Theme updates the file title is:
> 
> `2021-07-31-UL-ITS - Icon & Image Adjustment & Updates + Kanban Adjustments`
> 
> **Template:**
> 
> ```md
> ---
> tags: Journal/Update-Log
> 
> Date: 
> Title: 
> ---
> <i>**[[Update Log]]**
> **Project**:: [[]]
> **Link**:: []()
> </i>
> 
> # ` dv= this.Date` - ` dv= this.Project`
> - Updates/Fixes
> ```
> 
> **Result:**  
> ![Setup-Journal - Update Log Page.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal%20-%20Update%20Log%20Page.png)
> 
> # QuickAdd
> 
> > The QuickAdd plugin allows me to easily select whichever type of journal entry I want to create and enter the information I need.
> 
> ![Setup-Journal - QuickAdd Prompt.png](https://publish-01.obsidian.md/access/4663ec0147567a23b373ba037a568e2e/00%20Technical/2%20Images/I%20-%20Setup/Setup-Journal%20-%20QuickAdd%20Prompt.png)
> 
> My setup here is _very_ simple, just a template with some stuff in the file name and folder input and toggled on `Open` to open to the note once it’s created.
> 
> > **For simplicity:**  
> > `1` is the **File Name Format**  
> > `2` is the **Folder Format**
> 
> ---
> 
> **Bullet Journal** ― Template
> 
> 1.  `{{DATE:YYYY}}/{{DATE}}-J - {{VALUE:Title}}.md`
> 2.  `10 BuJo/1 Journal`
> 
> ---
> 
> **Dream Journal** ― Template
> 
> 1.  `{{DATE:YYYY}}/{{DATE}}-DJ - {{VALUE:Title}}.md`
> 2.  `10 BuJo/2 Dream Journal`
> 
> ---
> 
> **Workout Log** ― Template
> 
> 1.  `{{DATE:YYYY}}/{{DATE}}-WL-{{VALUE:A,T,L,W}} - .md`
> 2.  `10 BuJo/2 Dream Journal`
> 
> The template for this is different since I have different options I need to chose from. The letters are mostly the same choices from the table in the **[Journal Sections](https://publish.obsidian.md/slrvb/90+Site/Nebula/N_W+Bullet+Journal+Setup#Journal%20Sections)**. The only addition here is `W` which is just a blank template to add a different workout routine from the the usual arm/torso/leg.
> 
> **Template Note:**
> 
> ```eta
> <%* if (tp.file.title.match(/.*-WL-A/)) { -%>
> <% tp.file.include("[[Arm Day Template]]") %>
> <%* } else if (tp.file.title.match(/.*-WL-T/)) { -%>
> <% tp.file.include("[[Torso Day Template]]") %>
> <%* } else if (tp.file.title.match(/.*-WL-L/)) { -%>
> <% tp.file.include("[[Lower Body Day Template]]") %>
> <%* } else if (tp.file.title.match(/.*-WL-W/)) { -%>
> <% tp.file.include("[[Workout Log Template]]") %>
> <%* } else {} %>
> ```
> 
> This is the template that I have for quickadd to use when creating a note. The template will read the title of the journal entry and if it matches the letter, will add _that_ specific template to the note.
> 
> ---
> 
> **Conditions Log** ― Template
> 
> 1.  `{{DATE:YYYY}}/{{DATE}}-CL - {{VALUE:Title}}.md`
> 2.  `10 BuJo/4 Conditions Log`
> 
> ---
> 
> **Code Diary** ― Template
> 
> 1.  `{{DATE}}-CD-{{VALUE:Language}} - {{VALUE:Title}}.md`
> 2.  `10 BuJo/4 Code Diary`
> 
> ---
> 
> **Resonance Calendar** ― Template
> 
> 1.  `{{DATE}}-R - {{VALUE:Title}} -- {{VALUE:Creator}}.md`
> 2.  `10 BuJo/6 Resonance Log`
> 
> ---
> 
> **Update Log** ― Template
> 
> 1.  `{{DATE}}-UL-{{VALUE}} - .md`
> 2.  `10 BuJo/6 Update Log`
> 
> # Link Styling
> 
> > This is the css that I use to add the icons for each entry that you see in the screenshots of the **[0 BuJo MOCs](https://publish.obsidian.md/slrvb/90+Site/Nebula/N_W+Bullet+Journal+Setup#0%20BuJo%20MOCs)** Section.
> 
> ```css
> a.internal-link[href*="-J - "]::before {
>     content: "\ead6";
>     font-family: var(--rmx);
>     color: var(--bujo2);
> }
> a.internal-link[href*="-DJ - "]::before {
>     content: "\ea46";
>     font-family: var(--mdi);
>     color: #9bacad;
> }
> a.internal-link[href*="-UL"]::before {
>     content: "\f0d9";
>     font-family: var(--rmx);
>     color: #a483c3;
> }
> a.internal-link[href*="-CD"]::before {
>     content: "\e86f";
>     font-family: var(--mdi);
>     color: #74c897;
> }
> a.internal-link[href*="-R - "]::before {
>     content: "\eea7";
>     font-family: var(--rmx);
>     color: #e0a97b;
> }
> a.internal-link[href*="-CL"]::before {
>     content: "\ee10";
>     font-family: var(--rmx);
>     color: #e299d0;
> }
> a.internal-link[href*="-WL"]::before {
>     content: "\eae6";
>     font-family: var(--rmx);
>     color: #72b4b4;
> }
> ```
