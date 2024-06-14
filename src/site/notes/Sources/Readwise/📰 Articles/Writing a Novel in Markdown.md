---
{"dg-publish":true,"permalink":"/sources/readwise/articles/writing-a-novel-in-markdown/"}
---

> [!multi-column]
>
>> [!metadata]- Meta
>> **up**:: [[Atlas/📥 Sources\|📥 Sources]]
>> **type**:: #📥/📰 
>> **status**:: #📥/🟧  
>> **tags**:: #on/articles, #on/writing 
>> **topics**:: [[Cards/600 - Applied Sciences/Writing/🖋 Writing\|🖋 Writing]], [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
>
>> [!metadata]- Article Info
>> **Author**:: [[P.D. Workman\|P.D. Workman]]
>> **Title**:: Writing a Novel in Markdown
>> **URL**:: "https://pdworkman.com/writing-a-novel-in-markdown/"
>> **Reviewed Date**:: [[Calendar/Journal/Daily/2023-03-13\|2023-03-13]]
>> **Finished Year**:: [[2023\|2023]]

# Writing a Novel in Markdown

## Highlights





### id424555413 Folder Structure for Writing a Novel

> - Series folder (Obsidian vault)
> 	- Novel folder (Longform project folder)
> 		- archived (old drafts/versions of anything)
> 		- backup (compiled backups of book made every few days)
> 		-  characters (character motivations/notes for this book, different than the general notes on the characters in the series wiki)
> 		-  Drafts (Longform drafts folder)
> 			-  draft 0 – preplanning – snowflake, outline, etc.
> 			-  draft 1 … 2 … 3 …
> 			-  editing notes (notes of things to look at later, formatting, things to bring to the attention of my editor)
> 		-  graphics (covers, promotional graphics, ads, etc.)
> 		-  published (Vellum output folder for this novel)
> 		-  queries (saved search templates for Obsidian)
> 		-  research and notes (background for this novel)
> 		-  templates (character notes, snowflake template, word count tracking)
> 	-  Series wiki (linked “series Bible”) 
> 	
> 	[🔗](https://read.readwise.io/read/01gk55pbaeb2yh74bwsp28qjfv)

### id424555467

> File names
> I write one chapter per Markdown file. It may consist of 1-3 scenes. I like to use descriptive file name for the chapter so that I can quickly find what I am looking for and jump from one scene to another. They are numbered so that they can be sorted sequentially in any file viewer or editor. Some apps will let you manually arrange the chapters in the order you want them in, so you can drag them around until it suits you. I would suggest that once you are pretty sure of the order, you number them. I generally write in sequence, but I’ll write three or four chapters without a number, just in case I decide I want to add or move around a scene, and then number them once the sequence is solidified. <span class='highlight-link'>[🔗](https://read.readwise.io/read/01gk55qtf1qxskdm0qyb7qg66c)</span>

### id424556187

>  <span class='highlight-link'>[🔗](https://read.readwise.io/read/01gk5601ya6hh8xbydg0www98s)</span>

### id424556361

> I precede **character** names with **!** and **setting** names with **~** so that I can also search/filter them quickly from any file explorer. Why would I not just search Malachi instead of !Malachi? Because I don’t want to bring up every scene that Malachi is mentioned in, only the ones where he is a main character in the scene.
> I only use **POV** in books that have multiple points of view. If there is only one POV in the book, I don’t need to track it. Similarly, if every scene in the book uses Joe Blow’s POV, then I don’t include !Joe in the list of characters, because he would be listed for every single scene, there’s never any need to filter on him.
> **Day** helps me to keep track of day of the week or month, length of time between scenes, etc.
> **Note** is anything that I need to remember for later.
> **Draft** is the draft number
> **Grammarly** indicates whether I have run the scene through Grammarly. Yes—you can copy and paste Markdown text into Grammarly and it will not screw up the paragraph spacing, italics, etc. like many formats do. You can check the file and paste the results back into your Markdown file, and everything will still be properly formatted. <span class='highlight-link'>[🔗](https://read.readwise.io/read/01gk5621a34kfzk711kre5jjqr)</span>

### id424556363

> ![](https://pdworkman.com/wp-content/uploads/2021/12/Pasted-image-20211203193805-1.png) <span class='highlight-link'>[🔗](https://read.readwise.io/read/01gk5628wsjdrqfrkckqw5dzy8)</span>

### id424556379

> Marking scene breaks
> If you are importing into Vellum, then you want all of your scene breaks to be properly marked. Trust me, you don’t want to have to input all of your scene breaks after the file has been imported!
> If you use `***` or `---` to mark your scene breaks, then they will be converted to a horizontal line <hr> when you convert to HTML. And horizontal lines are **not** recognized by Vellum as scene breaks.
> If you **use `+++` to mark your scene breaks** (you don’t need to center it), it will not be converted to a horizontal line when you convert to HTML. It will stay as a `+++`. And **`+++` is recognized as as scene break by Vellum.** <span class='highlight-link'>[🔗](https://read.readwise.io/read/01gk563dkdqbpq2qzp0qw4sdae)</span>

### id424556386

> My Obsidian Longform plugin formatting
> You can format your editing and preview screens in Obsidian using CSS formatting that only applies to Longform project files.
> My edit screen:
> ![](https://pdworkman.com/wp-content/uploads/2021/12/Pasted-image-20211203202348.png)
> My preview screen:
> ![](https://pdworkman.com/wp-content/uploads/2021/12/Pasted-image-20211203202405.png)
> My sample CSS
>     /* Font for the markdown source panel */
>     .Longform-leaf .cm-s-Obsidian
>     {
>         font-family: Arial;
>         font-size: 1.1em;
>         line-height: 2em;
>     }
>     
>     .Longform-leaf .cm-comment
>     {
>         font-family: monospace;
>         font-size: .8em;
>         line-height: 1em;
>     }
>     
>     .Longform-leaf .cm-header-1
>     {
>       font-family: Garamond;
>       font-size: 1.5em;
>       line-height: 2em;
>     }
>     
>     
>     /* Font for the markdown preview panel */
>     .Longform-leaf .markdown-preview-view {
>         font-family: Garamond;
>         font-size: 1.2em;
>             text-indent: 1em;
>         text-align: justify;
>     }
>     
>     .Longform-leaf h1 {
>       font-family: Garamond;
>       font-size: 2em;
>       text-indent: 0em;
>       margin-top: 1em;
>     }
>     
>     .Longform-leaf p {
>       margin-bottom: -15px;
>       line-height: 1.3em;
>     }
>     
>     .Longform-leaf {
>       --background-primary: antiquewhite;
>       --background-primary-alt: white;
>       --background-secondary: white;
>       --background-secondary-alt: white;
>       --text-selection: #aaa;
>       --text-normal: black;
>         --text-faint: blue;
>       color: black;
>     }
>     
>     .Longform-leaf .suggestion-item.is-selected {
>       background-color: var(--text-accent);
>     }
>     
>     .Longform-leaf .markdown-preview-view blockquote {
>         border-color: darkgrey;
>         font-size: 95%;
>         text-align: left;
>         hyphens: auto;
>         word-break: keep-all;
>         color: black; # you need to define
>         font-color: #aacdbe;
>         line-height: 1.3;
>         padding: 10px 2% 10px 2%;
>         margin-top: 15pt;
>         margin-bottom: 15pt;
>     } <span class='highlight-link'>[🔗](https://read.readwise.io/read/01gk563vmw9paevh86rhrpfggs)</span>

### id424556397

> Using Word Count Dashboard in Obsidian
> I use the [Word Count Dashboard](https://gist.github.com/chrisgrieser/ac16a80cdd9e8e0e84606cc24e35ad99) to keep track of the word count in my Longform Project Draft folder. It is a little complex to set up and took a bit of playing around to get right.
> This is what the top portion of my query template looks like:
>     ---
>     cssclass: wordcountTable
>     ---
>     
>     
>     
>     
> And this is what the query results look like:
> ![](https://pdworkman.com/wp-content/uploads/2021/12/Pasted-image-20211203203209.png) <span class='highlight-link'>[🔗](https://read.readwise.io/read/01gk564bkbpza7m3rerpr8tf0n)</span>

### id424556485

> he two compiling tools that I have used are:
> [Notebooks App](https://www.notebooksapp.com/)
> You can compile all files in a folder to one HTML file by clicking the three dots at the top of the panel and selecting compile. By default, the first line of the file becomes an H1 header. By default, the first line of the file is the file name, and changing one changes the other. This prevents you from using a YAML header in Notebooks App, since the three dashes need to be the first three characters in the file.
> [Obsidian Longform Plugin](https://giters.com/chetachiezikeuzor/longform)
> You can compile all files in the draft folder of a Longform project by going to the Longform panel compile tab and clicking compile. Select the checkbox to make the Scene titles become H1 headers. <span class='highlight-link'>[🔗](https://read.readwise.io/read/01gk5664g8zchm652v8a1d2pxr)</span>

### id424556527

> Pandoc
> The Obsidian Longform Plugin will compile all of the Scenes into one long MD (markdown) file.
> To convert from MD to HTML, you will want to use Pandoc. Pandoc is a command line file converter that lets you convert from one file format to another in Terminal. But don’t panic. If you are using Obsidian, install the [Pandoc Plugin](https://github.com/OliverBalfour/obsidian-pandoc). (If you are using another Markdown editor, you will need to see what the options are available, learn Pandoc command line prompts, or use an online tool such as StackEdit to convert the file from MD to HTML.)
> To convert using Pandoc plugin in Obsidian: navigate to the compiled MD file and click on it. Pull up the command palette (cmd-p) and type HTML. You should see “Pandoc Plugin: Export as HTML (without Pandoc)” Select this option to convert your MD file to an HTML file. <span class='highlight-link'>[🔗](https://read.readwise.io/read/01gk566j8vy8psw6j43t5p084n)</span>