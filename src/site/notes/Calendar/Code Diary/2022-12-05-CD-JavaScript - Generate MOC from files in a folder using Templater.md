---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-05-cd-java-script-generate-moc-from-files-in-a-folder-using-templater/","title":"Generate MOC from files in a folder using Templater"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> type:: #log/code 
> language:: [[Sources/Tools + Plugins/JavaScript\|JavaScript]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]], [[Sources/Tools + Plugins/Plugin - Templater\|Plugin - Templater]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Generate MOC from files in a folder using Templater
**Language::**  [[Sources/Tools + Plugins/JavaScript\|JavaScript]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]

## Summary
> Ask user to select folder to generate MOC for all files in this folder, all files in subfolders will be included

## Code
> Is it possible to get a bulleted list of all the files included in a specific folder in this format ?
> - `[[name of file 1]]`
> - `[[name of file 2]]`


```JavaScript
<%*  
// ask user to select folder to generate MOC for all files in this folder
// all files in subfolders will be included
const folders = this.app.vault.getAllLoadedFiles().filter(i => i.children).map(folder => folder.path);
const folderChoicePath = await tp.system.suggester(folders, folders);
if (folderChoicePath != null) {
    new Notice(`Folder selected: ${folderChoicePath}`, 5000);

    const files = app.vault.getMarkdownFiles();
    const filesInFolder = new Array();
    console.log("folderChoicePath: " + `${folderChoicePath}`)
    files.forEach((file) => {
        //console.log("file.path: " + `${file.path}`)
        if (file.path.includes(folderChoicePath)) {
            filesInFolder.push(file.basename)
        };
    })
    const filesList = new Array();
    filesInFolder.forEach((file) => {
        //console.log(file)
        filesList.push('\n - [[' + file + ']]')
    });
    const folderChoice = folderChoicePath.split("/").slice(-1)
    const fileName = folderChoice + " MOC"
    //files sorted case insensitive
    const content = "## " + folderChoice + " MOC " + "\n" + filesList.sort((a, b) => a.toLowerCase().localeCompare(b.toLowerCase())).join('')

    // create new file with a list of files in folder
    const tFolder = app.vault.getAbstractFileByPath(folderChoicePath)
    // if file exist, do not create file
    if (await app.vault.exists(`${folderChoicePath}/${fileName}.md`)) {
        new Notice(`Unable to create. File already exists: ${folderChoicePath}/${fileName}.md`, 5000)
    } else {
        await tp.file.create_new(content, fileName, true, tFolder)
        new Notice(`Created new MOC: ${folderChoicePath}/${fileName}.md`, 5000);
    }
} else {
    new Notice(`No folder selected`, 5000);
}
_%>


```

> Hi, thank you for your response. Is there a way to get the list in the active file without creating a new file, and to replace something in the code so that it always checks the same folder.

```JavaScript
// Check the folder specified below and build a list of all markdown files
// all files in subfolders will be included

// = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =
// MacOS example, Modify folderChoicePath
folderChoicePath = "resources/health/"
// If you are on Windows, try: "resources\health\"
// = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =

if (folderChoicePath != null) {
	new Notice(`Folder: ${folderChoicePath}`, 5000);
	let filesInFolder = new Array();
	console.log("folderChoicePath: " + `${folderChoicePath}`)
	filesInFolder =  app.vault.getMarkdownFiles().filter(file => file.path.includes(folderChoicePath)).map(tFile=>tFile.basename)
	const filesList = new Array();
	filesInFolder.forEach((file) => {
		filesList.push('\n - [[' + file + ']]')
	});
	const folderChoice = folderChoicePath.split("/").slice(-2).join("")
	const fileName = folderChoice + " MOC"
	//files sorted case insensitive
	const heading = "## " + folderChoice.charAt(0).toUpperCase() + folderChoice.slice(1)+ " MOC"
	const content = heading + "\n" + filesList.sort((a, b) => a.toLowerCase().localeCompare(b.toLowerCase())).join('')

	// insert the list of files in the active file
	tR+=content
	new Notice(`Created new MOC`, 5000);	
} else {
	new Notice(`No folder selected`, 5000);
}
_%>

```

> Thank you, this helped me immensely. I modified this slightly to generate a table rather than a list. The table has 3 columns.
> 1. the file link
> 2. a description column (to be filled in)
> 3. links to generated headers for more detailed descriptions of the files.
> 
> The level 2 headers using the file name are automatically generated after the table.
> Here is my modifications for anyone needing this...

```JavaScript
<%*
// Check the folder specified below and build a list of all markdown files
// all files in subfolders will be included

// = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =
// MacOS example
folderChoicePath = "Templates/"
// If you are on Windows, try: "resources\health\"
// Note: "/" works fine under Windows 10
// = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =

if (folderChoicePath != null) {
	new Notice(`Folder: ${folderChoicePath}`, 5000);
	let filesInFolder = new Array();
	let headings = new Array();
	console.log("folderChoicePath: " + `${folderChoicePath}`)
	filesInFolder =  app.vault.getMarkdownFiles().filter(file => file.path.includes(folderChoicePath)).map(tFile=>tFile.basename)
	const filesList = new Array();
	filesList.push('\n| Template | Description | Detailed Notes |\n| -------- | ----------- | -------------- |')
	filesInFolder.forEach((file) => {
		filesList.push('\n|[[' + file + ']] | - | [[#' + file + ']] |')
		headings.push('\n## ' + file + '\n')
	});
	const folderChoice = folderChoicePath.split("/").slice(-2).join("")
	const fileName = folderChoice + " MOC"
	//files sorted case insensitive
	const heading = "## " + folderChoice.charAt(0).toUpperCase() + folderChoice.slice(1)+ " MOC"
	let content = heading + "\n" + filesList.sort((a, b) => a.toLowerCase().localeCompare(b.toLowerCase())).join('')
	content = content + "\n" + headings.sort((a, b) => a.toLowerCase().localeCompare(b.toLowerCase())).join('')

	// insert the list of files in the active file
	tR+=content
	new Notice(`Created new MOC`, 5000);	
} else {
	new Notice(`No folder selected`, 5000);
}
_%>
```
## Explanation
- 

## Result

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]