---
{"dg-publish":true,"permalink":"/extras/templates/template-paper/","title":"{{title}}"}
---


> [!metadata]- Meta
> **up**:: 
> **type**:: #📥/📜
> **status**:: #📥/🟥 
> **tags**:: {{allTags}}
> **topics**:: 
> **links**::

# {{title}}

<%*
	let title = "{{title | replace(':', '') | replace('#', '') | replace('^', '') | replace('|', '') | replace('\[', '') | replace('\]', '') | replace('\\', '') | replace('/', '')}}";
	let date = tp.date.now("YYYY-MM-DD");
	await tp.file.rename(`${title}`);
_%>

> [!info]- Info
> **zotero_link**:: {{pdfZoteroLink}}
> **author**:: {{authors}} {{directors}}
> **url**:: {{url}}
> **doi**:: {{doi}}
> **citekey**:: {{citekey}}
{% for relation in relations -%}
{%- if relation.citekey -%}
> **related**:: {{relation.citekey}}
{% endif -%}
{%- endfor %}

> [!links]- Related
>  | File | created | modified | tags | type |
> | ---- | ------- | -------- | ---- | ---- |
> 
{ .block-language-dataview}

> [!abstract]+
> **abstract**:: {{abstractNote}}

> [!tldr]- Hypothesis
> **hypothesis**:: 

> [!summary]- Summary of Key Points
> 


## Highlights

| <mark class="hltr-grey">Highlight Color</mark> | Meaning                        |
| ---------------------------------------------- | ------------------------------ |
| <mark class="hltr-red">Red</mark>              | Disagree with Author           |
| <mark class="hltr-orange">Orange</mark>        | Definition                     |
| <mark class="hltr-yellow">Yellow</mark>        | Interesting Point by Author    |
| <mark class="hltr-green">Green</mark>          | Important To Me                |
| <mark class="hltr-blue">Blue</mark>            | Other sources cited or related |
| <mark class="hltr-magenta">Magenta</mark>      | Confused or questions          |
| <mark class="hltr-purple">Purple</mark>        | Section Heading                |

{% for annotation in annotations -%}
{%- if annotation.annotatedText -%} 
### id0{{annotation.id}}

<mark class="hltr-{{annotation.colorCategory | lower}}">{{annotation.annotatedText}}</mark> [Page {{annotation.page}}](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.page}}&annotation={{annotation.id}})

{%- endif %} 
{%- if annotation.imageRelativePath -%}
### id0{{annotation.id}}

![[{{annotation.imageRelativePath}}\|{{annotation.imageRelativePath}}]] [Page {{annotation.page}}](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.page}}&annotation={{annotation.id}})

{%- endif %} 
{%- if annotation.comment %} 
- [N] {{annotation.comment}} 

{%- endif %} 

{% endfor %}

---
up:: 





