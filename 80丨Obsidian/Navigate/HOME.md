---
cssclasses:
  - myhome
---
# HOME

- ### Learning
	- [今日复盘](obsidian://adv-uri?vault=Note&daily=true)
	- [[../../10丨MOC/JavaMOC|JavaMOC]]
	- Rust
	- Python
- ### Projects
	- [[../Tasks/IDEA|IDEA]]
	- [[../../10丨MOC/LeetCode|LeetCode]]
	- Python

- ### Setting
	- [[../../10丨MOC/Obsidian指南|Obsidian指南]]
	- Linux

**PROJECT TRACKING**
```dataviewjs
// 胶囊标签生成器
const badge = (text, color) => `<span style="display:inline-block; padding:2px 8px; border-radius:12px; font-size:12px; font-weight:bold; background-color:${color}20; color:${color}; border:1px solid ${color}40;">${text}</span>`
//进度条
const bar = (val, max) => {
	const pct = Math.round(val/max*100) || 0;
	return `<div style="display:flex; align-items:center; gap:8px;"><progress value="${val}" max="${max}" style="width:60px; height:8px;"></progress><small style="color:var(--text-muted)">${pct}%</small></div>`
}
// 灰色#9e9e9e 绿色#4caf50 蓝色#2196f3
//LeetCode统计
const count = dv.pages('"50丨LeetCode" and #hot100').length;
dv.table(
    ["项目", "标准", "进度","状态"],
        [
            ["[[../../10丨MOC/LeetCode|Hot100]]", "**刷题**", bar(count,100),badge("进行中", "#4caf50")]
        ]
    );
```

> [!note] 服务器 & 资源
> ```dataviewjs
> // --- 逻辑定义 ---
> // 计算剩余天数
> const daysLeft = (dateStr) => {
>   const left = Math.ceil((new Date(dateStr) - new Date()) / (1000 * 60 * 60 * 24));
>   const color = left < 30 ? "#ff5252" : (left < 90 ? "#ff9800" : "#4caf50");
>   return `<span style="color:${color}; font-weight:bold">${left} 天</span>`;
> }
> 
> dv.table(
> 	["资源名称", "配置/备注", "剩余有效期"],
> 	[
> 		[
> 			"☁️ **[阿里云·成都](https://swasnext.console.aliyun.com/)**", 
> 			"<code style='background:transparent; border:1px solid var(--text-muted); color:var(--text-normal)'>2H2G</code><br><small>NextCloud</small>", 
> 			daysLeft("2026-07-24")
> 		],
> 		[
> 			"☁️ **[Ucloud·香港](https://console.ucloud.cn/)**", 
> 			"<code style='background:transparent; border:1px solid var(--text-muted); color:var(--text-normal)'>2H4G</code><br><small>WebSite</small>", 
> 			daysLeft("2026-07-05")
> 		],
> 		[
> 			"🔗 **[moningf.top](https://dc.console.aliyun.com/)**", 
> 			"<small>阿里云域名</small>", 
> 			daysLeft("2029-01-22")
> 		]
> 	]
> )
> ```

<br>

> [!quote] 个人状态
> ```dataviewjs
> let ftMd = dv.pages("").file.sort(t => t.cday)[0]
> let total = parseInt([new Date() - ftMd.ctime] / (60*60*24*1000))
> let allFile = dv.pages('!"misc/templates"').file
> 
> let totalTask = allFile.tasks.length+"个待办。 "
> 
> dv.paragraph(`🌱 已坚持 **${total}** 天 <br> 📝 累计 **${allFile.length}** 篇笔记 | 🏷️ **${allFile.etags.distinct().length}** 个标签 | 📖 **${allFile.tasks.length}** 个待办`)
> ```
