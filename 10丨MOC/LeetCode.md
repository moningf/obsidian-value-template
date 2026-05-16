> [!note] 刷题记录
> ```dataviewjs
> let total = dv.pages('"50丨LeetCode"')
> let hot100 = dv.pages('"50丨LeetCode" and #hot100')
> dv.paragraph(`📝 累计刷题 **${total.length}** 个 <br>🔥  Hot100 **${hot100.length}** 个`) 
> ```

**hot100**
```dataviewjs
let hot100 = dv.pages('"50丨LeetCode" and #hot100').file.link
dv.list(hot100)
```