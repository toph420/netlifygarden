---
{"dg-publish":true,"permalink":"/calendar/code-diary/2023-01-27-cd-css-gradient-colored-callouts/","title":"Gradient colored callouts"}
---

> [!metadata]- Meta
> **up**:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]
> **type**:: #log/code 
> **tags**:: #on/snippets 
> **language**:: [[Sources/Tools + Plugins/CSS\|CSS]]
> **program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
> **topics**:: [[Cards/600 - Applied Sciences/Technology/Coding/Coding\|Coding]]


# Gradient colored callouts
**Language::**  [[Sources/Tools + Plugins/CSS\|CSS]]
**Program**:: [[Sources/Tools + Plugins/Obsidian\|Obsidian]]
**Link**::

## Summary
> A cool snippet for callouts

## Code

```CSS
@import url(https://fonts.bunny.net/css?family=spectral:200,200i,300,300i,400,400i,500,500i,600,600i,700,700i,800,800i);
@font-face {
	font-family: "Alegreya SC";
	font-style: normal;
	font-weight: 400;
	font-display: swap;
	src: url(https://fonts.gstatic.com/s/alegreyasc/v15/taiOGmRtCJ62-O0HhNEa-Z6v2ZA.woff2) format("woff2");
	unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
  }
  /* latin-ext */
  @font-face {
	font-family: "Alegreya SC";
	font-style: normal;
	font-weight: 400;
	font-display: swap;
	src: url(https://fonts.gstatic.com/s/alegreyasc/v15/taiOGmRtCJ62-O0HhNEa-Z6h2ZAJaQ.woff2) format("woff2");
	unicode-range: U+0100-024F, U+0259, U+1E00-1EFF, U+2020, U+20A0-20AB, U+20AD-20CF, U+2113, U+2C60-2C7F, U+A720-A7FF;
  }
  /* latin */
  @font-face {
	font-family: "Alegreya SC";
	font-style: normal;
	font-weight: 700;
	font-display: swap;
	src: url(https://fonts.gstatic.com/s/alegreyasc/v15/taiTGmRtCJ62-O0HhNEa-ZYU_IU2SKo.woff2) format("woff2");
	unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
  }
  /* latin-ext */
  @font-face {
	font-family: "Alegreya SC";
	font-style: normal;
	font-weight: 700;
	font-display: swap;
	src: url(https://fonts.gstatic.com/s/alegreyasc/v15/taiTGmRtCJ62-O0HhNEa-ZYU_IU4SKqGFQ.woff2) format("woff2");
	unicode-range: U+0100-024F, U+0259, U+1E00-1EFF, U+2020, U+20A0-20AB, U+20AD-20CF, U+2113, U+2C60-2C7F, U+A720-A7FF;
}

[data-callout=quote].callout.callout {
	font-family: "Spectral", -apple-system, BlinkMacSystemFont, "Segoe UI",
	"Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", serif;
	background-color:transparent;
	border: none;
	display: flex;
	flex-direction: column-reverse;
}
[data-callout=quote] .callout-content > p {
	margin-top: 0;
}
[data-callout=quote] .callout-title a {
	font-family: "Alegreya SC", "Spectral", serif;
	font-variant-ligatures: none;
	text-decoration: none;
}
  [data-callout=quote].callout.callout .callout-icon {
	display: none;
  }

[data-callout=quote] .callout-content.callout-content {
	padding: 0;
	font-size: 1.4em;
	text-align: center;
	font-weight: 300;
	font-variant-ligatures: common-ligatures;
	font-feature-settings: "liga";
}
[data-callout=quote] .callout-content.callout-content::before {
	font-size: 1.4em;
	content: "\201C";
	font-weight: 900;
}
  [data-callout=quote] .callout-content.callout-content::after {
	font-size: 1.4em;
	content: "";
	font-weight: 900;
  }

  [data-callout=quote] .callout-title.callout-title {
	padding-top: 0;
	justify-content: center;
	color: var(--text-normal);
  }
  [data-callout=quote] .callout-title.callout-title .callout-title-inner {
	font-weight: 300;
  }
```

## Result

![[2023-01-27-CD-CSS - Gradient colored callouts - example.png\|2023-01-27-CD-CSS - Gradient colored callouts - example.png]]

---
up:: [[Calendar/+ MOCs/🧪 Code Diary\|🧪 Code Diary]]