---
{"dg-publish":true,"permalink":"/calendar/code-diary/2022-12-03-cd-css-css-code-icon/","title":"CSS Code Icon"}
---

> [!metadata]- Meta
> up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]], [[Calendar/+ MOCs/📓 Journal\|Journal]]
> categories:: #log/code 
> language:: [[Sources/Tools + Plugins/CSS\|CSS]]
---

# CSS Code Icon

**Language**:: [[Sources/Tools + Plugins/JavaScript\|JavaScript]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]

## Code
> To draw a code icon with CSS, you can use the `:before` or `:after` pseudo-element to create a content block, and then use the `content` property to add the code character (`&lt;/&gt;`) inside the block. Then, you can use various CSS properties, such as `border`, `border-radius`, `background-color`, and `box-shadow`, to style and customize the appearance of the icon.
> Here is an example of a code icon created with CSS:

```css
.code-icon:before { 
	content: "&lt;/&gt;"; 
	font-family: monospace; 
	font-size: 36px; 
	color: #333; 
	border: 1px solid #ccc;
	border-radius: 5px; 
	background-color: #eee; 
	box-shadow: 2px2px 3px rgba(0,0,0,0.5); padding: 10px; 
	margin: 20px; 
}
```
> This CSS code will create a code icon that looks like this:
> `<div class="code-icon"></div>`
> You can further customize the appearance of the icon by adjusting the various CSS properties, such as the font, size, color, border, and shadow.


## Explanation


## Result
- 
---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]