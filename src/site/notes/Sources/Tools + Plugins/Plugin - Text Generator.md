---
{"dg-publish":true,"permalink":"/sources/tools-plugins/plugin-text-generator/","title":"Plugin - Text Generator"}
---

> [!metadata]- Meta
> **up**:: [[Sources/Tools + Plugins/Tools + Plugins\|Tools + Plugins]]
> **type**:: #📥/🛠 
> **status**:: #📥/🟧 
> **tags**::  #on/plugins, #on/ai 
> **topics**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> **links**:: [[Sources/Tools + Plugins/Chat GPT\|Chat GPT]], [[Cards/600 - Applied Sciences/Technology/AI/🤖 Artificial Intelligence\|🤖 Artificial Intelligence]]

# Plugin - Text Generator

> Utilizes Chat GPT to generate text


> [!abstract]+ From [[Nicole VanderHoeven\|Nicole VanderHoeven]]
> > Source:: https://notes.nicolevanderhoeven.com/Obsidian+Text+Generator+plugin
> 
> Text Generator is a [Obsidian](https://notes.nicolevanderhoeven.com/Obsidian) [plugin](https://notes.nicolevanderhoeven.com/Obsidian+Plugins) that uses [AI](https://notes.nicolevanderhoeven.com/Artificial+Intelligence) (specifically, [GPT-3](https://notes.nicolevanderhoeven.com/GPT-3)) to create text according to given prompts.
> <iframe width="560" height="315" src="https://www.youtube.com/embed/OergqWCdFKc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
> 
> The Text Generator plugin can also be used as a tool for [Divergent thinking](https://notes.nicolevanderhoeven.com/Divergent+thinking). [[1\|1]](https://publish.obsidian.md/#fn-1-40f196befa45eb5a)
> 
> ## Usage
> 
> ### Generate Text
> 
> After installing the plugin, open or create a note in Obsidian and type out a prompt. A prompt can consist of a question, sentence, or request, such as:
> 
> -   `Tell me a secret.`
> -   `What is emergence?`
> -   `What is the difference between backend and frontend performance testing?`
> -   `Narrate the harrowing escape of three plucky adventurers from the clutches of the shadowy fiend called The Forgotten.`
> 
> Then, either use the default hotkey (`CMD/CTRL+J`) or open up the command pane and select `Text Generator: Generate Text!`
> 
> In a few seconds, your text will be generated.
> 
> Increase `max_tokens`
> 
> Was the generated text cut off abruptly? If so, that may be because of the default limit to how much the plugin will generate for you. To change this, go into the plugin settings and adjust the `max_tokens` value to a higher number, depending on how long you want the generated text to be.
> 
> ### Install packages
> 
> The Text Generator plugin comes with a templates package manager that contains prompts. The two available right now are:
> 
> -   Default prompts
> -   DallE-2 prompts
> 
> These "templates" are different from what we usually mean by [templates](https://notes.nicolevanderhoeven.com/Obsidian+Templater) when working in Obsidian. Instead, these templates are more like predefined commands for what or how the plugin will generate. For example, the prompts packages above provide options like:
> 
> -   Generate an anime photo
> -   Generate tags for your content
> -   Generate an outline
> -   Simplify
> -   Summarize
> -   Brainstorm ideas
> 
> ### Create templates
> 
> With the Text Generator plugin, you can also create templates _using_ the prompts. Usually, this involves selecting a prompt and then either pre-seeding data (having other data in a template note) or using variables to be dynamically generated when the template is applied.
> 
> #### Create a new template
> 
> 1.  Create a new note that you'll use as a template.
> 2.  From the Command Pane, select `Text Generator: Create a Template`.
> 3.  Choose the file path and filename for the template (if you want to change it).
> 4.  In the note, enter a prompt. Ex: `Brainstorm content using {{title}}.` Also add `title` (or any variables you set) as values to the `required_values` field.
> 5.  Create a new note, or open the note that you'd like to use the template in.
> 6.  From the Command Pane, select `Text Generator: Generate and insert template`. The template you created will be included in the list.
> 7.  Select your template to run it.
> 
> ---
> 
> 1.  Raftis, R. (2023). _How to use ChatGPT for divergent thinking in Obsidian and PKMs._ Retrieved from [https://medium.com/@ricraftis/how-to-use-chatgpt-for-divergent-thinking-in-obsidian-and-pkms-3bb829428149](https://medium.com/@ricraftis/how-to-use-chatgpt-for-divergent-thinking-in-obsidian-and-pkms-3bb829428149)

---
up:: [[🏠 Home\|🏠 Home]]

