---
cssclasses:
  - hide-properties
banner: "[[banner.png]]"
banner_position: "10"
---



```dataviewjs
const hour = new Date().getHours();
let greeting = (hour >= 5 && hour < 12) ? "早上好" :
               (hour >= 12 && hour < 18) ? "下午好" : "晚上好";

dv.el("div", `${greeting}，忆雨~`, {cls: "homepage-header shake"});
```



[[Knowledge Dashboard]] 📊

```columns
id: zIEpr2GqYdEMaamgvJqO9
===
## [图书馆](图书馆)



===
## [[笔记]]

===
## [[写题]]

```

---





