---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-04-cd-type-script-average-size-of-all-markdown-file-in-vault/","title":"Average Size of All Markdown File in Vault"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> categories:: #log/code 
> language:: [[Sources/Tools + Plugins/TypeScript\|TypeScript]]
> program:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> topics:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]
---

# Average Size of All Markdown File in Vault

## Summary
> Reads the content of all Markdown files in the Vault and returns the average document size:

## Code
```typescript
import { Notice, Plugin } from "obsidian";

export default class ExamplePlugin extends Plugin {
  async onload() {
    this.addRibbonIcon("info", "Calculate average file length", async () => {
      const fileLength = await this.averageFileLength();
      new Notice(`The average file length is ${fileLength} characters.`);
    });
  }

  async averageFileLength(): Promise<number> {
    const { vault } = this.app;

    const fileContents: string[] = await Promise.all(
      vault.getMarkdownFiles().map((file) => vault.cachedRead(file))
    );

    let totalLength = 0;
    fileContents.forEach((content) => {
      totalLength += content.length;
    });

    return totalLength / fileContents.length;
  }
}
```


---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]