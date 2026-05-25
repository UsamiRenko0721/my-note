---
cssclasses:
  - dashboard
banner: 
banner_position: 
up:
  - "[[🏠 Home]]"
---

# 📊 知识仪表板

**欢迎来到您的知识管理中心**  
这里汇总了所有笔记的统计数据、最近活动和学习进度。仪表板自动更新，帮助您快速掌握知识库全貌。

---

## 📈 核心统计

```dataviewjs
// 基本统计数据
const totalNotes = dv.pages().length;
const today = dv.date('today');
const recentNotes = dv.pages().where(p => p.file.ctime >= dv.date('today') - dv.duration('7 days')).length;

// 按主要文件夹统计
const folders = [
  {name: "Atlas/读书", display: "📚 读书笔记"},
  {name: "Atlas/写题", display: "✍️ 习题解答"},
  {name: "Atlas/笔记", display: "📝 个人笔记"},
  {name: "Calendar/Daily", display: "📅 每日记录"}
];

dv.paragraph(`**总计**: ${totalNotes} 篇笔记 | **最近7天**: ${recentNotes} 篇更新`);

// 文件夹统计表格
dv.table(
  ["类别", "笔记数量", "最新更新"],
  folders.map(f => {
    const pages = dv.pages(`"${f.name}"`);
    const latest = pages.length > 0 
      ? pages.sort(p => p.file.mtime, 'desc')[0].file.mtime.toFormat("yyyy-MM-dd")
      : "无";
    return [f.display, pages.length, latest];
  })
);
```

---

## 🎯 按学科分类

```dataviewjs
// 学科分类统计（基于文件夹路径）
const subjects = [
  {path: "Pathira", name: "热力学与统计物理", emoji: "🔥"},
  {path: "Nakahara", name: "数学物理", emoji: "📐"},
  {path: "Jackson", name: "电动力学", emoji: "⚡"},
  {path: "Peskin", name: "量子场论", emoji: "🌀"},
  {path: "Yau", name: "综合物理", emoji: "🌟"},
  {path: "CFT", name: "共形场论", emoji: "✨"},
  {path: "东京大学", name: "名校试题", emoji: "🏫"},
  {path: "中科大", name: "国内试题", emoji: "🇨🇳"}
];

const subjectData = subjects.map(sub => {
  const notes = dv.pages().where(p => 
    p.file.path.includes(sub.path) && 
    !p.file.path.includes("Templates")
  );
  return {
    subject: `${sub.emoji} ${sub.name}`,
    count: notes.length,
    latest: notes.length > 0 
      ? notes.sort(p => p.file.mtime, 'desc')[0].file.mtime.toFormat("MM-dd")
      : "-"
  };
}).filter(item => item.count > 0);

if (subjectData.length > 0) {
  dv.table(
    ["学科", "笔记数", "最近更新"],
    subjectData.map(item => [item.subject, item.count, item.latest])
  );
} else {
  dv.paragraph("暂无学科分类数据。建议为笔记添加学科标签。");
}
```

---

## 🗓️ 最近活动

### 最近更新的笔记
```dataview
table file.mtime as 修改时间, up as 上级链接
from ""
where file.mtime >= date(today) - dur(7 days)
sort file.mtime desc
limit 10
```

### 最近创建的笔记
```dataview
table file.ctime as 创建时间, file.folder as 文件夹
from ""
where file.ctime >= date(today) - dur(14 days)
sort file.ctime desc
limit 10
```

---

## 📚 学习进度

### 待完成的习题
```dataview
table chapter as 章节, difficulty as 难度, file.ctime as 创建时间
from "Atlas/写题"
where !completed
sort file.ctime asc
limit 15
```

### 读书笔记最新进展
```dataview
table up as 关联, related as 相关, date as 日期
from "Atlas/读书"
sort date desc
limit 10
```

---

## 🏃 习惯跟踪

### 最近学习记录
```dataview
table 物理, 数学, 英语, file.day as 日期
from "Calendar/Daily"
where 物理 or 数学 or 英语
sort file.day desc
limit 7
```

> 📊 **完整习惯统计**：查看 [[⚛️Habits Tracker]] 获取详细热图

---

## 🧭 快速导航

```dataviewjs
// 常用笔记快速链接
const quickLinks = [
  {path: "🏠 Home.md", name: "🏠 主页"},
  {path: "图书馆.md", name: "📖 图书馆"},
  {path: "笔记.md", name: "📝 笔记总览"},
  {path: "Atlas/写题", name: "✍️ 习题中心"},
  {path: "Calendar/⚛️Habits Tracker.md", name: "📊 习惯跟踪"},
  {path: "Atlas/读书/Pathira", name: "🔥 热统笔记"}
];

dv.paragraph("**常用入口**");
quickLinks.forEach(link => {
  const page = dv.page(link.path);
  if (page) {
    dv.paragraph(`• ${link.name}: [[${link.path}]]`);
  } else {
    // 如果是文件夹
    const pages = dv.pages(`"${link.path}"`);
    if (pages.length > 0) {
      dv.paragraph(`• ${link.name}: [[${link.path}]] (${pages.length}篇)`);
    }
  }
});
```

---

## 🔍 探索工具

### 查找没有上级链接的笔记
```dataview
table file.folder as 文件夹
from ""
where !up and !file.folder.includes("Templates") and !file.folder.includes("Calendar")
limit 20
```

### 查找没有标签的笔记
```dataview
table file.folder as 文件夹
from ""
where !tags and !file.folder.includes("Templates") and !file.folder.includes("x")
limit 15
```

---

## 📝 使用说明

1. **自动更新**：本仪表板使用Dataview查询，数据实时更新
2. **自定义修改**：根据需要调整查询条件或添加新的统计维度
3. **学科分类**：当前基于文件夹路径识别学科，建议为笔记添加`学科:`元数据以提升准确性
4. **习题跟踪**：为习题笔记添加`completed: true/false`字段以启用进度跟踪

---

## 🛠️ 待优化功能

- [ ] 添加间隔重复复习队列
- [ ] 集成知识掌握程度评估
- [ ] 添加学习时间统计
- [ ] 创建知识图谱可视化

---

**最后更新**: `=dateformat(file.mtime, "yyyy-MM-dd HH:mm")`  
**生成方式**: Obsidian Dataview + 自定义查询

> 💡 **提示**: 定期查看此仪表板，掌握知识库动态，发现学习盲点。
