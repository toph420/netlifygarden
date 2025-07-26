---
{"dg-publish":true,"permalink":"/extras/templates/template-zotero/","title":"{{title}}","tags":["📥","zotero"]}
---


# {{title}}

> [!info]- Info
> **Zotero Link**: {{pdfZoteroLink}}
> **Author**: {{authors}} {{directors}}
> **URL**: {{url}}
> **DOI**: {{doi}}
> **Cite Key**: {{citekey}}
{% for relation in relations -%}
{%- if relation.citekey -%}
> **Related**:: {{relation.citekey}}
{% endif -%}
{%- endfor %}

> [!links]- Related
>  | File | created | subcategories |
> | ---- | ------- | ------------- |
> 
{ .block-language-dataview}

> [!abstract]- Abstract
> **Abstract**: {{abstractNote}}

> [!tldr]- Hypothesis
> **Hypothesis**:: 

> [!summary]- Summary of Key Points
> 

## Highlights

| <mark class="hltr-grey">Highlight Color</mark> | Meaning                                |
| ---------------------------------------------- | -------------------------------------- |
| <mark class="hltr-red">Red</mark>              | Disagree with Author                   |
| <mark class="hltr-orange">Orange</mark>        | Definition                             |
| <mark class="hltr-yellow">Yellow</mark>        | Interesting Point by Author            |
| <mark class="hltr-green">Green</mark>          | Important To Me                        |
| <mark class="hltr-blue">Blue</mark>            | Other sources cited, related, examples |
| <mark class="hltr-magenta">Magenta</mark>      | Confused or questions                  |
| <mark class="hltr-purple">Purple</mark>        | Section Heading                        |
| <mark class="hltr-grey">Grey</mark>            | Look this up, dig into further         |

---

{% persist "annotations" %}
{% set newAnnotations = annotations | filterby("date", "dateafter", lastImportDate) %}
{% if newAnnotations.length > 0 %}
***Imported: {{importDate | format("YYYY-MM-DD h:mm a")}}***

{% for a in newAnnotations -%}
{%- if a.annotatedText -%} 
### id0{{a.id}}

<mark class="hltr-{{a.colorCategory | lower}}">{{a.annotatedText}}</mark> [Page {{a.page}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}}&annotation={{a.id}})

{%- endif %} 
{%- if a.imageRelativePath -%}
### id0{{a.id}}

![[{{a.imageRelativePath}}\|{{a.imageRelativePath}}]] [Page {{a.page}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}}&annotation={{a.id}})

{%- endif %} 
{%- if a.comment %} 
- [N] {{a.comment}} 

{%- endif %} 

{% endfor %}

{% endif %}
{% endpersist %}





