---
{"dg-publish":true,"permalink":"/cards/000-knowledge-management/css-snippets/title-bar/"}
---

# Title bar
```css
/* Title Bar without text, custom colour */
.titlebar {
  background-color: black; (match to your theme);
  border-bottom:1px solid darkslategrey;
}

.titlebar-text,
.titlebar-button {
  display: none;
}

/* Frameless = no titlebar */
.is-frameless {
  padding-top:0px !important;
}

/* hide title bar text */
.titlebar-text {
  color: transparent;
}
```
