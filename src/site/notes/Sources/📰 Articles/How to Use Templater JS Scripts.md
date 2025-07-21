---
{"dg-publish":true,"permalink":"/sources/articles/how-to-use-templater-js-scripts/","title":"How to Use Templater JS Scripts","tags":["📥/📰","📥/🟨","on/plugins"]}
---


# How to Use Templater JS Scripts

- link:: [how-to-use-templater-js-scripts - shabeblog](https://shbgm.ca/blog/obsidian/how-to-use-templater-js-scripts)

## Summary
- This is a great tutorial about the usefulness of keeping separate [[Sources/Tools + Plugins/Plugin - Templater\|Plugin - Templater]] files instead of using them in templates themselves. 

## Notes

**Step 1: Write .js file**
```js
async function notice(tp) {
    const text = await tp.system.prompt("What's Good?")
    new Notice(text, 5000)
}

module.exports = notice
```

**Step 2: Write the Templater command**  
`<%* tp.user.notice(tp) %>`

> [!NOTE] **A note on file names**  
> *it appears that Templater uses the name of the JS file and not the function name when you call the user command. I suggest naming the file the same as your exported function to avoid confusion.*

**Step 3: Run your new Command**  
Create a new note with the "Notice" template. The script prompts for input and a notification pops up with what you typed.

### Breaking it down

#### The JS File
- We created a new function called `notice`. Whatever we set as paramters to `notice` are the arguments we provide the command. In this case, we want to run other `tp` methods so we set a `notice(tp)` parameter. We can include other parameters if we want.
- It is an `async` function because we're doing some asynchronous JS, thus `await` it.
- `const text = await tp.system.prompt("What's Good?")`
	- Because we passed in `tp`, we can use all of the available Templater command methods. In this case we are displaying a prompt.
- `new Notice(text, 5000)`
	- Since our script is running inside [[Sources/Tools + Plugins/Obsidian\|Obsidian]] we can also access the full Obsidian API. In this case we're creating a `new Notice` and displaying the `text` provided in the prompt. We can also access anything off of `app` such as `app.vault` or `app.workspace`.
- `module.exports = notice`
	- **This line is important!** This is how Templater will be able to read the `notice` function we created. Just **make sure to export** your user function.

#### The Templater Command
- Since we put all our logic inside the `notice.js` file, the Templater command is simple.
- `<%* %>`
	- This particular command does not have any output, thats why we use the `*` instead of `<% %>`. If we want to return something from our JS file, we could use the standard Templater syntax.
- `tp.user.notice(tp)`
	- This is calling the function we created in `notice.js`. Two things to note here:
		1. All user specified functions will be under `tp.user`
		2. Remember how we specified `notice(tp)` parameter when writing the `notice` function? We're supplying `tp` as an argument when calling the function. We could supply additional arguments if our JS function required them.

#### Advanced Usage
- Let's take a command that creates a new block-reference:
```js
<%*
let cmEditorAct = this.app.workspace.activeLeaf.view.sourceMode.cmEditor;
let curLine = cmEditorAct.getCursor().line;
cmEditorAct.setSelection({ line: curLine, ch: 0 }, { line: curLine, ch: 9999 });

function createBlockHash() {
	let result = '';
	var characters = 'abcdefghijklmnopqrstuvwxyz0123456789';
	var charactersLength = characters.length;
	for ( var i = 0; i < 7; i++ ) {
		result += characters.charAt(Math.floor(Math.random() * charactersLength));
	}
	return result;
}

let id = createBlockHash();
let block = ![[${tp.file.title}#^${id}]].split("\n").join("");
navigator.clipboard.writeText(block).then(text => text);
tR = tp.file.selection() + ^${id}.split("\n").join("");
%>
```

- And convert it into a JS file + Command. 
- **The JS File:** (this goes in the Templater Scripts folder)
```js
function addBlockRef(tp) {
    
	//Use the Obsidian API to get the CodeMirror Editor
    const editor = app.workspace.activeLeaf.view.editor
    const cursorLine = editor.getCursor().line
    
	//Set the selection in the CodeMirror Editor
    editor.setSelection({line: cursorLine, ch: 0}, {line: cursorLine, ch: 9999})
	const id = createBlockHash();
	const block = `![[${tp.file.title}#^${id}]]`.split("\n").join("");

	// Copy the block reference to the clipboard
	navigator.clipboard.writeText(block).then(text => text);

	//Return the selected text and the generated block id
	return tp.file.selection() + `^${id}`.split("\n").join("");
}

//A simple function to create a random block id
function createBlockHash() {
	let result = '';
	var characters = 'abcdefghijklmnopqrstuvwxyz0123456789';
	var charactersLength = characters.length;
	for ( var i = 0; i < 7; i++ ) {
		result += characters.charAt(Math.floor(Math.random() * charactersLength));
	}
	return result;
}

//export the addBlockRef function
module.exports = addBlockRef
```

- **The Templater Command:** (this goes in your template file)
- `<% tp.user.addBlockRef(tp) %>`

### Ideas
- I could use this functionality to create cleaner, modular templates.
- For example, each type of source has it's own Metadata, can I separate these using a script?

---
up:: [[Sources/Tools + Plugins/Plugin - Templater\|Plugin - Templater]]
