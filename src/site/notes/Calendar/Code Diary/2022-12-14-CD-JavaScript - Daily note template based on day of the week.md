---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-14-cd-java-script-daily-note-template-based-on-day-of-the-week/","title":"Daily note template based on day of the week"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> categories:: #log/code 
> tags:: #to/implement 
> language:: [[Sources/Tools + Plugins/JavaScript\|JavaScript]], [[Sources/Tools + Plugins/Plugin - Templater\|Plugin - Templater]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Daily note template based on day of the week
**Language::**  [[Sources/Tools + Plugins/JavaScript\|JavaScript]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**:: [Daily note template based on day of the week (bonus: link note to current day) · Discussion #240 · SilentVoid13/Templater · GitHub](https://github.com/SilentVoid13/Templater/discussions/240#discussion-3378883)

## Summary
> Daily note template based on day of the week, see discussion for more details and use cases

## Code

> I wanted a solution to populate different Day Planner schedules based on the current day of the week, and with some help from @shabegom I have achieved this with the following:
> 
> User JS scripts:
> ### scheduleTemplate.js
> ```js
> function scheduleTemplate(tp) {
>   switch (parseInt(moment(tp.file.title).format('d'))) {
>     case 1: return tp.file.include("[[Schedule - 01 Monday]]")
>     case 2: return tp.file.include("[[Schedule - 02 Tuesday]]")
>     case 3: return tp.file.include("[[Schedule - 03 Wednesday]]")
>     case 4: return tp.file.include("[[Schedule - 04 Thursday]]")
>     case 5: return tp.file.include("[[Schedule - 05 Friday]]")
>     case 6:
>     case 0: return tp.file.include("[[Schedule - Weekend]]")
>     default: return tp.file.include("[[Schedule - +Weekday]]")
>   }
> }
> 
> module.exports = scheduleTemplate
> ```
> ### command.js
> ```js
> function command(action) {
>   const allCommands = app.commands.listCommands();
>   const command = allCommands.filter(
>     (command) => command.name.toUpperCase() === action.toUpperCase().trim()
>   )[0];
>   app.commands.executeCommandById(command.id);
>   return '';
> };
> module.exports = command;
> ```
> 
> ### Daily note Template
> ```js
> <% tp.user.scheduleTemplate(tp) %>
> <%* if(moment(tp.file.title).isSame(new Date(), "day")) tp.user.command("Day Planner: Link today's Day Planner to the current note") %>
>```

## Explanation


> ### Discussion
> **Link**: https://github.com/SilentVoid13/Templater/discussions/240#discussioncomment-829917
> 
> I'll jump in, since I was planning on writing a how-to anyhow (so future-me doesn't forget how I set this all up 😆)
> 
> -   You need to create a folder for scripts someplace inside your vault.
>     -   I just put mine in the root, and called it TemplaterJS, but you can put it anywhere inside your vault and call it whatever you like.
>     -   You should also have a folder for templates, but you've probably already got that set up 😀
> -   In the Templater preferences, put the path (from your vault root) to your scripts folder in the "Script files folder location"
> -   You don't need to turn on the "Enable System Commands" or put anything in the function name or system commands boxes
> -   Using a text editor, create a file called scheduleTemplate.js in the scripts folder you just created. Paste in the contents you see above. Do the same for command.js
>     -   It's really important to use a text editor, like NotePad or TextEdit (or even better, VSCode or Atom if you've already got one of them) rather than a word processor like Word or Pages.
> -   If you look at the contents of the scheduleTemplate.js, you'll see a line that says `switch (parseInt(moment(tp.file.title).format('d'))) {`. What that's doing is telling the program to look at the file title and treat it like a date, figure out which day of the week it is, and return a number from 0 - 6 (so this trick only works on notes whose name is based on a date, like daily notes). Then it has a separate case for each number, and includes a file for each day.
>     -   Depending on where you live, either Sunday or Monday may be 0, so you may need to change which templates load for which case
>     -   You can also change the names of the templates being included. The script is using the file title (or more specifically, what you would put in double wiki brackets to link to that file, which gets a little more complicated if there are files with duplicate names 🙄 😛 )
>     -   You can put the same template for more than one day. (When I was a student, I had the same schedule on M/W/F and on T/Th)
> -   In your templates folder, create a file (just in Obsidian -- you don't need a text editor for this 😀) for each different schedule you want to embed
>     -   In each of these schedule templates, put whatever custom bits you want to have for that/those specific day(s)
> -   Also create a file for your daily notes template, and into that put all the stuff you want to appear on _every_ day. Wherever you want the stuff that's specific for each day, paste the `<% tp.user.scheduleTemplate(tp) %> <%* if(moment(tp.file.title).isSame(new Date(), "day")) tp.user.command("Day Planner: Link today's Day Planner to the current note") %>` code.
> 
> For example, here's my Daily Notes template (I'm also using the Tasks plugin, which is what all the fol-de-rol at the bottom is about):
> 
> ```
> # Daily Log -- {{ date:MMM D, YYYY}}
> 
> [[<% tp.date.now("YYYY[ -- Year]", 0, tp.file.title) %> |<% tp.date.now("YYYY", 0, tp.file.title) %>]] » [[<% tp.date.now("YYYY-MM", 0, tp.file.title) %> -- Month#<% tp.date.now("YYYYMMDD dddd, MMM D, YYYY", 0, tp.file.title) %> | <% tp.date.now("MMMM", 0, tp.file.title) %>]]  » [[<% tp.date.weekday("YYYY-MM-DD", 0, tp.file.title) %> -- Week#<% tp.date.now("YYYYMMDD dddd, MMM D, YYYY", 0, tp.file.title) %> | Week <% tp.date.now("ww", 0, tp.file.title) %>]]
> [[<% tp.date.now("YYYYMMDD", -1, tp.file.title) %> | ⇦ Previous Day]] | [[<% tp.date.now("YYYYMMDD", +1, tp.file.title) %> | Next Day ⇨]] 
> 
> <% tp.user.daily_schedule(tp) %>
> <%* if(moment(tp.file.title).isSame(new Date(), "day")) tp.user.command("Day Planner: Link today's Day Planner to the current note") %>
> ---
> 
> ## Tasks
> ### Overdue 
> - Personal
> 	```tasks
> 	not done
> 	path includes Task List
> 	due before {{ date:YYYY-MM-DD }}
> 	```
> 
> - Work
> 	```tasks
> 	not done
> 	path includes Work
> 	due before {{ date:YYYY-MM-DD }}
> 	```
> 
> ### Due today
> - Personal
> 	```tasks
> 	not done
> 	path includes Task List
> 	due on {{ date:YYYY-MM-DD }}
> 	```
> 
> - Work
> 	```tasks
> 	not done
> 	path includes Work
> 	due on {{ date:YYYY-MM-D D}}
> 	```
> 
> ### Due w/in 7 days
> - Personal
> 	```tasks
> 	not done
> 	path includes Task List
> 	heading includes running
> 	due after {{ date:YYYY-MM-DD }}
> 	due before {{ date+7d:YYYY-MM-DD }}
> 	```
> 
> - Work
> 	```tasks
> 	not done
> 	path includes Work
> 	due after {{ date:YYYY-MM-DD }}
> 	due before {{ date+7d:YYYY-MM-DD }}
> 	```
> 
> ### No due date
> - Personal
> 	```tasks
> 	not done
> 	path includes Task List
> 	no due date
> 	```
> 
> - Work
> 	```tasks
> 	not done
> 	path includes Work
> 	no due date
> 	```
> 
> ### Done today
> - Personal
> 	```tasks
> 	path includes Task List
> 	done on {{ date:YYYY-MM-DD }}
> 	```
> 
> - Work
> 	```tasks
> 	path includes Work
> 	done on {{ date:YYYY-MM-DD}}
> 	```
> 
> ---
> ## Notes
> 
> - Personal
> 	- 
> 
> 
> - Work
> 	-  
> ```
> 
> You can see that under the breadcrumb, I'm using [@deathau](https://github.com/deathau)'s script to load my daily schedule. Here's an example of my Friday schedule:
> 
> ```
> ---
> ## Day Planner
> - [ ] 06:00 Get up, brush teeth, make tea, etc
> - [ ] 06:30 Prep on computer
> 	- [ ] check email
> 	- [ ] preview day 
> 		- [ ] check calendar and weekly and monthly pages
> 		- [ ] what's for dinner? does anything need thawed?
> 	- [ ] protein bar breakfast of champions
> - [ ] 07:00 Professional development
> 	- [The Complete JavaScript Course 2021: From Zero to Expert!](https://www.udemy.com/course/the-complete-javascript-course/)
> 	- [[The Complete JavaScript Course 2021]]
> - [ ] 08:00 Work
> - [ ] 11:30 Lunch 
> - [ ] 12:00 Nap
> - [ ] 12:30 BREAK
> - [ ] 13:00 [[Dev Meeting]]
> - [ ] 14:00 Work
> - [ ] 17:00 Cook dinner
> - [ ] 18:00 Eat dinner
> - [ ] 18:30 Clean up
> - [ ] 19:00 Practice Guitar
> - [ ] 19:30 Kid 1's Bedtime
> - [ ] 20:00 Free Time / Fallback Guitar Practice
> - [ ] 20:30 Kid 2's Bedtime
> - [ ] 21:15 Work out
> - [ ] 21:45 Shower
> - [ ] 22:30 END
> ```
> 
> The super awesome thing about [@deathau](https://github.com/deathau)'s script is that if you create your daily note on that day, it automatically links it to the Day Planner plugin, which is way spiffy! 😀

## Alternative

> Slight tweak of the function but allows customization of notes within obsidian. This way you can modify the included files within obsidian including using [[]] to autocomplete
>```js
> function scheduleWeekday(tp, files) {
>   switch (parseInt(moment(tp.file.title).format('d'))) {
> 
>     case 1:
>     case 2:
>     case 3:
>     case 4:
>     case 5:
>       return tp.file.include(files.weekday)
> 
>     case 0:
>     case 6: return tp.file.include(files.weekend)
>   }
> 
> }
> module.exports = scheduleWeekday;
> ```
> Invocation:
> ```js
> <% 
>     tp.user.scheduleDaily(tp, {
>           weekday:  "[[Utilities/Templater/Templates/Blocks/Process/P-Weekdays]]",
>           weekend:      "[[P-Weekends]]",
>     }) 
> %>
> ```

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]