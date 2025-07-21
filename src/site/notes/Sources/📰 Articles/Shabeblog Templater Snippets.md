---
{"dg-publish":true,"permalink":"/sources/articles/shabeblog-templater-snippets/","title":"Shabeblog Templater Snippets","tags":["📥/📰","📥/🟨","on/coding","on/pkm","on/snippets"]}
---



# Shabeblog Templater Snippets

## Summary
> A great list of some creative [[Sources/Tools + Plugins/Plugin - Templater\|Plugin - Templater]] scripts and snippets.

### Conditionally Update a Frontmatter Value Using MetaEdit
Say you have a frontmatter key status and you want to setup a button that will progress the value from one status to the next.
```js
<%*
const file = tp.file.find_tfile(tp.file.title);
const {update} = app.plugins.plugins["metaedit"].api;
const status = tp.frontmatter.status;

if (status === "In Progress") {
	await update("status","Complete",file);
}
if (status === "Backlog") {
	await update("status", "In Progress", file);
}
-%>
```

### Rename an Untitled File
I use this snippet in my new file template to quickly name my notes. The newTitle variable can be used later in the note to get the note title.

```js
<%*
const title = tp.file.title;
if (title.includes("Untitled")) {
	const newTitle = await tp.system.prompt("File Name");
	await tp.file.rename(newTitle);
}
-%>
```

### Replace a [ ] with [>] in a Selection
This snippet takes the selected text, which it assumes is a task, and converts the empty checkbox to [>]. You could reuse it to do any text manipulation on a selection.

```js
<%*
const selection = tp.file.selection();
if (selection) {
	const replace = selection.split("\n").map(select => {
	    if (select.includes("- [ ]")) {
	        select = select.replace("[ ]", "[>]");
	    }
	return select;
}).join("\n");
	tR += replace;
} else {
    new Notice("Text must be selected");
};
%>
```

### Use Nl-dates and Metaedit together
Let's get fancy. This snippet updates a frontmatter key due with the date supplied in a prompt using the MetaEdit plugin. The date supplied can be in natural language like "next Friday" and we use the Natural Language Dates plugin to convert it to "YYYY-MM-DD" format.

```js
<%*
const file = tp.file.find_tfile(tp.file.title);
const {update} = app.plugins.plugins["metaedit"].api;
const nlInput = await tp.system.prompt("What Date");
const date = app.plugins.plugins["nldates-obsidian"].parseDate(nlInput).formattedString;
await update("due", date, file);
%>
```

### Basic read/replace
Read the contents of the note, find the line with the content you want to change (in this example it is an inline meta field) and write back to the file with the updated line.

```js
<%*
const content = tp.file.content.split("/n").map(line => {
   if (line.includes("status:")) {
        line = "status::green_square:";
    }
    return line;
}).join("\n");
const file = tp.file.find_tfile(tp.file.title);
await app.vault.modify(file, content);
%>
```

### Choose a File and Append Some Text
Use a suggester to select a file from all the files in your vault. Then append some text to the selected file.

```js
<%*
const files = app.vault.getMarkdownFiles();
const select = await tp.system.suggester(f => f.basename, files);
await app.vault.append(file, 'some text to append');
%>
```

### Replace an Argument in a Template before Running
Using a keyword $ARG we can quickly replace some text in a template note before using it to create a new file.

```js
<%*
const arg = tp.frontmatter.arg;
const template = await tp.file.include("[[Template]]");
const final = template.replace("$ARG",arg); 
//$ARG is put in the template where you want to replace with the argument
tp.file.create_new(final, "New Note");
%>
```

### Fetch a Random Note
Gets all the files in your vault and returns a random one. You could further filter this down to files in a specific folder.

```js
<%*
const files = app.vault.getFiles();
const random = Math.floor(Math.random() * (files.length - 1));
const randomNote = files[random];
%>
```
Usage: Today's random note is [[<% randomNote.basename %> \|<% randomNote.basename %> ]]

### Get All Frontmatter Tags
Sure you could use tp.frontmatter, but sometimes you want to read from the metadataCache directly. This snipped uses a Set, which is just a fancy array where all the values are unique (no duplicates).

```js
const tags = Array.from(new Set(Object.values(app.metadataCache.metadataCache).filter(cache => cache.frontmatter).map(cache => cache.frontmatter.tags)));
```

### Select a Tag or Make a New One
Gets all the tags in your vault. Shows a suggester to pick a tag, If "Make New" is chosen it shows a prompt to make a new tag. The final output is inserted into the note.

```js
<%*
const tags = Object.keys(app.metadataCache.getTags());
let selection = await tp.system.suggester([...tags, "Make New"], [...tags, "Make New"]);
if (selection === "Make New") {
    selection = await tp.system.prompt("new tag");
}
tR += selection;
%>
```

### Create a New Note for Every Link in a File
Say you've got a note and it has a bunch of links, but none of those links resolve to created notes yet. This snippet will create all those files.

```js
const currentFile = tp.file.find_tfile(tp.file.title);
const links = app.metadataCache.getFileCache(currentFile)?.links;
if (links) {
   links.forEach(link => { 
       await tp.file.create_new("", link.name);
    });
};
```

### Build a Calendar with Links to Daily Notes
This involves a bunch of math, but the output is pretty cool! A text calendar with daily notes links.

| sun | mo | tu | we | th | fr | sat |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|

```js
<%*
const days = parseInt(moment().daysInMonth()) + parseInt(moment().startOf("month").format("d"))
const table = []
table.push("|")
for (let i = 0; i < days; i++) {
   if (i > 0 && i % 7 === 0) {
        table.push("\n|")
   }
   table.push(`[[${moment().day(i).format("YYYY-MM-DD")}]]|`)
}
tR += table.join("")
%>
```

### Move Tasks from Yesterday Daily Note to Today's
Looks for tasks under a ## Header and returns them. You could add this to your daily notes template to always move tasks ahead.

```js
<%*
// get the TFile of yesterday's note
const previousDay = tp.file.find_tfile(tp.date.now("YYYY-MM-DD", -1)); 
// read the contents of that note
const previousDayContent = await app.vault.read(previousDay); 
// replace with whatever the header is
const header = "## The Header"; 
// turn the content of the note into an array and find the index of the header
const headerIndex = previousDayContent.split("\n").indexOf(header); 
//splice starts at the index and deletes the number of items in the array based on the second value provide. It returns the deleted items.
const tasks = previousDayContent.split("\n").splice(headerIndex, 6); 
// removes the first element of the array which is the header
tasks.shift(); 
//turn the array back into a string and return it to the note
tR += tasks.join("\n"); 
%>
```

### Check if a Folder Exists and Create it if not
I probably wouldn't use this method anymore, but keeping it around as an example.

```js
<%*
const exists = app.vault.adapter.exists("/Folder");
if (exists) {
	await  tp.file.move("");
} else {
	await app.vault.adapter.mkdir("/Folder");
	await tp.file.move("");
}
%>
```

### Get Inline Meta from within a Note
This snippet creates an object `dataview` that contains key/value pairs of any inline meta within the note it is run. For example if you had a meta value foo:: bar, dataview.foo would equal bar

```js
<%*
const content = tp.file.content.split("\n");
const dataview = content.filter(line => line.match(/\w+\:\: \w+$/)).reduce((acc, line) => {
    const [key, value] = line.split(":: ");
    acc[key] = value;
    return acc;
}, {})
%>
```

### Load a Selected Template from a Suggester
Show a suggester with different template options. Load in the selected template from the suggester. Check out that switch statement!

```js
<%*
const choice = await tp.system.suggester(["Simple Note", "Book", "Music", "MOC"], ["Simple Note", "Book", "Music", "MOC"]);
let output = "";
switch(choice) {
	case "Book":
		output = await tp.file.include("[[-Book]]");
		break;
	case "Music":
		output = await tp.file.include("[[-Music]]");
		break;
	case "MOC":
		output = await tp.file.include("[[-MOC]]");
		break;
	default:
		new Notice("No Matching Template");
};
   
tR += output;
%>
```

### Add/edit Metadata in All Notes inside a Folder
Select a folder from a suggester, enter a key and value using a prompt and this will iterate over every note in the folder and update the specified meta key.  
*Note: only works with folders in vault root. It won't find a nested folder. Requires MetaEdit plug.*

```js
<%*
const {update} = app.plugins.plugins["metaedit"].api;
const root = app.vault.getRoot();
const folders = root.children.filter(child => child.children);
const selectedFolder = await tp.system.suggester(e => e.name, folders, false, "Choose a Folder");
const metaKey = await tp.system.prompt("What Meta Key?");
const metaValue = await tp.system.prompt("Meta Value");
if (selectedFolder.children) {
	selectedFolder.children.forEach(async (child) => {
	    const {frontmatter} = app.metadataCache.getCache(child.path)
		const content = await app.vault.read(child);
		if (frontmatter) {
			if (Object.keys(frontmatter).includes(metaKey)) {
				update(metaKey, metaValue, child);
			} else {
				const contentArray = content.split("\n");
				contentArray.splice(1, 0, `${metaKey}: ${metaValue}`);
				await app.vault.modify(child, contentArray.join("\n"));
			}
		} else {
			const updatedContent = `---\n${metaKey}: ${metaValue}\n---`.concat(content);
			await app.vault.modify(child, updatedContent);
		}
	});
} else {
	new Notice("No Notes in Selected Folder");
}
%>
```

### Remove Duplicate Templates and Renumber the Content
I honestly have no idea what this does and no recollection of writing it. Looks pretty fancy though!

```js
<%*
const file = tp.file.find_tfile(tp.file.title)
const content = tp.file.content.split("\n")
const duplicateIds = []
content.filter(line => line.match(/^\[\^.*\]:/)).map(item => {
	const [number, content] = item.split(":")
	return {number, content}
}).reduce((acc, footnote) => {
	if (!acc[0]) {
		acc.push(footnote)
		return acc
	}
	acc.forEach(item => {
		if (item.content === footnote.content) {
				duplicateIds.push({real: item.number, duplicate: footnote.number})
		} 
	})	
		acc.push(footnote)
		return acc
}, [])
const updatedContent = content.map(line => {
	duplicateIds.forEach(({real, duplicate}) => {
			if (line.includes(duplicate) && !line.startsWith(duplicate)) {
					line = line.replace(duplicate, real)
			}
			if (line.startsWith(duplicate)) {
					line = "$RENUM"
			}
	})
	return line
}).filter(line => line !== "$RENUM").join("\n")
await app.vault.modify(file, updatedContent)
%>
```

### Output Based on Weekday/Weekend
Two techniques for only outputting a value if the day is a weekday. It expects your note title to have the format YYYY-MM-DD -- dddd but the first example could be easily adapted for other formats.

```js
<%*
const date = moment(tp.file.title, "YYYY-MM-DD -- dddd").day();
console.log(date);
if (date < 6) {
	tR += "School:: ";
}
-%>
```

```js
<%*
const dow = tp.file.title.split("-- ")[1];
console.log(dow);
if (!dow.includes("Saturday") && !dow.includes("Sunday")) {
	tR +="School:: ";
}
-%>
```

---
up:: [[Atlas/📥 Sources\|📥 Sources]]