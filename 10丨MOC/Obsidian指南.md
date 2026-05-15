> [!note] Obsidian插件
> ```dataviewjs
> let total = dv.pages('"40丨Tools/Obsidian" and #obsidina插件')
> dv.paragraph(`📝 插件指南 **${total.length}** 篇`) 
> ```

```dataviewjs
let total = dv.pages('"40丨Tools/Obsidian" and #obsidina插件')
dv.list(total.file.link)
```