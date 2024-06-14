---
{"dg-publish":true,"permalink":"/cards/000-knowledge-management/obsidian-ai-assistant/","title":"Obsidian AI Assistant"}
---

> [!metadata]- Meta
> **up**:: [[🏠 Home\|🏠 Home]]
> **type**:: #📝 
> **status**:: #📝/🌞
> **tags**::  
> **topics**:: 
> **links**::


# Obsidian AI Assistant

> Christian Houmann's AI script use cases and guides

- Original email: [Spark | AI Assistant for Obsidian](https://app.sparkmailapp.com/web-share/cdBbOIZDC6bOqP3S8ZQGfixdS-LCZEip5jvFzhFs)
- [How to set up & use AI Assistant for Obsidian - YouTube](https://www.youtube.com/watch?v=C4hCESoNo7k)
- [AI Assistant for Obsidian · GitHub](https://gist.github.com/chhoumann/73f7ded929561963fc1cf2d8db17ecfc)
- [Twitter showcase thread](https://link.mail.beehiiv.com/ss/c/3_TOaAJVYZDPKItpOraZVJelRGT5vBMkSt7k6MHR5Z6VKMKvjPwRwZvjZUAhxGuOLHOPTTm5bgtPmOD--VqjSR9macITJPAsTxIZcpfDtnjwKnXWvGLZHcuT9wvsccaR1fmAwj0WkkQSBUinrttIid4AnWIBhGKmOoAP_fNxnMsKviRyTn0LTbh9838iTZYwaCmvk7ElhfLZ90nfdnx99g/3vf/SYqcVyrhRfy9Lna3q-6ogg/h13/xInnpfCPHxPweTykTQ9Rjf-xS79xj4APbKyl5zv-F88 "https://link.mail.beehiiv.com/ss/c/3_TOaAJVYZDPKItpOraZVJelRGT5vBMkSt7k6MHR5Z6VKMKvjPwRwZvjZUAhxGuOLHOPTTm5bgtPmOD--VqjSR9macITJPAsTxIZcpfDtnjwKnXWvGLZHcuT9wvsccaR1fmAwj0WkkQSBUinrttIid4AnWIBhGKmOoAP_fNxnMsKviRyTn0LTbh9838iTZYwaCmvk7ElhfLZ90nfdnx99g/3vf/SYqcVyrhRfy9Lna3q-6ogg/h13/xInnpfCPHxPweTykTQ9Rjf-xS79xj4APbKyl5zv-F88") (for inspiration)
-  An [OpenAI API key](https://link.mail.beehiiv.com/ss/c/AGoTYpTLBGKDqcKt5qZvn-BbAODHW1hpAzrzaigcaTcDKsDaqbYqR9SKJ8zyc4vDqPOP-tpaY0-1iD5z5CCYA8ZFkzjoi2WzcHC349ThC_cmsf6EstjZkLRlBMuqViHLsWceJ1eIHCq45B44Yym6leceNBAO7NvnTsnvX5OYWprjCxIadqExIS0gLaKieG9W/3vf/SYqcVyrhRfy9Lna3q-6ogg/h14/0jZxQQdbtv7I1LzcBYsVWfGFknJlH6fbIwDXwHy0qWw "https://link.mail.beehiiv.com/ss/c/AGoTYpTLBGKDqcKt5qZvn-BbAODHW1hpAzrzaigcaTcDKsDaqbYqR9SKJ8zyc4vDqPOP-tpaY0-1iD5z5CCYA8ZFkzjoi2WzcHC349ThC_cmsf6EstjZkLRlBMuqViHLsWceJ1eIHCq45B44Yym6leceNBAO7NvnTsnvX5OYWprjCxIadqExIS0gLaKieG9W/3vf/SYqcVyrhRfy9Lna3q-6ogg/h14/0jZxQQdbtv7I1LzcBYsVWfGFknJlH6fbIwDXwHy0qWw")
-  The QuickAdd plugin for Obsidian - found in the community plugin store
-  Got stuck? Want more power? Here’s the [QuickAdd documentation](https://link.mail.beehiiv.com/ss/c/ctF1_5-SDv8sjYs4zLDW7Cg7Q92qRZXCGpijRz8nWwaDWCI_NFBYUv_JJLh5ZBhCrZOhNG8ktzxvK3dJNf_lN1r0cwb0BUIO71sw-8kotISxzS5JzOdhxukvzgrjp5h4vA_63qzQJhzZxl8slF7oZknR2--9ztDdYA0FETv6YARIXLoMIdil5gC_uZPkMCIh/3vf/SYqcVyrhRfy9Lna3q-6ogg/h15/S9DY5ISZ_H7dd4zBlwY1WB2Wbyv4Adg0F6LokMVM4Rg "https://link.mail.beehiiv.com/ss/c/ctF1_5-SDv8sjYs4zLDW7Cg7Q92qRZXCGpijRz8nWwaDWCI_NFBYUv_JJLh5ZBhCrZOhNG8ktzxvK3dJNf_lN1r0cwb0BUIO71sw-8kotISxzS5JzOdhxukvzgrjp5h4vA_63qzQJhzZxl8slF7oZknR2--9ztDdYA0FETv6YARIXLoMIdil5gC_uZPkMCIh/3vf/SYqcVyrhRfy9Lna3q-6ogg/h15/S9DY5ISZ_H7dd4zBlwY1WB2Wbyv4Adg0F6LokMVM4Rg"). You can also just hit reply to this email, and I’ll try to help :)


**Original System Prompt**
> `As an AI assistant within Obsidian, your primary goal is to help users manage their ideas and knowledge more effectively. Format your responses using Markdown syntax. Please use the [[Obsidian]] link format. You can write aliases for the links by writing [[Obsidian|the alias after the pipe symbol]]. To use mathematical notation, use LaTeX syntax. LaTeX syntax for larger equations should be on separate lines, surrounded with double dollar signs ($$). You can also inline math expressions by wrapping it in $ symbols. For example, use $$w_{ij}^{	ext{new}}:=w_{ij}^{	ext{current}}+etacdotdelta_jcdot x_{ij}$$ on a separate line, but you can write "($eta$ = learning rate, $delta_j$ = error term, $x_{ij}$ = input)" inline.`



---
up:: [[🏠 Home\|🏠 Home]]

