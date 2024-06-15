---
{"dg-publish":true,"permalink":"/calendar/code-diary/2023-03-12-cd-quickadd-move-a-specific-file-to-a-folder-with-a-command-or-click/","title":"Move a specific file to a folder with a command or click"}
---

> [!metadata]- Meta
> **up**:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> **type**:: #log/code 
> **tags**:: #on/snippets 
> **language**:: [[Sources/Tools + Plugins/Plugin - Quickadd\|Quickadd]]
> **program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> **topics**:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Move a specific file to a folder with a command or click
**Language::**  [[Quickadd\|Quickadd]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**URL**:: [Script to move current file to a specific folder · chhoumann/quickadd · Discussion #386 · GitHub](https://github.com/chhoumann/quickadd/discussions/386)

## Summary
> How to move a file to a specific folder with a single command / click.

## Code

Recently, a question popped up on the Obsidian discord about how to move a file to a specific folder with a single command / click.  
Here's a script you can use to do that. Just add it to a macro and bind that to a command/hotkey.

```js
const targetDir = "targetFolderHere"; // e.g. '1 - Areas'. Don't end with a slash. Empty for root directory.

module.exports = async () => {
    const currentFile = app.workspace.getActiveFile();
    if (!currentFile) {
        new Notice(`No active file to move.`);
        return;
    }

    if (currentFile.parent.name === targetDir) {
        new Notice(`File is already in target folder.`);
        return;
    }

    try {
        await app.vault.rename(currentFile, `${targetDir}/${currentFile.name}`);
    } catch (error) {
        new Notice(`Error moving file: ${error}`, 15000);

        const folder = app.vault.getAbstractFileByPath(targetDir);
        if (!folder) {
            new Notice(`Target folder '${targetDir}' does not exist.`, 15000);
        }
    }
};
```


---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]