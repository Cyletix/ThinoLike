# **Obsidian 笔记管理工具「MemoFlow」**

## **简介**

**「MemoFlow」** 是一个基于 **DataviewJS** 的仅使用dataviewjs实现的单文件笔记管理界面, 灵感来自于Obsidian插件Thino, 集 **快速笔记录入** 与 **高效笔记筛选** 于一体, 让 Obsidian 用户能够更高效地记录、管理和回顾笔记。

该工具包含两个独立模块：

1. **MemoInput** - 笔记录入模块：快速记录任务、想法或时间戳笔记, 并自动归档到合适的文件。
2. **TasksView** - 笔记筛选模块：智能筛选 Obsidian 笔记, 提供即时的任务、日记和灵感回顾功能。

## **功能特点**

### **MemoInput（笔记录入模块）**

✅ **文本输入框**：快速输入内容, 支持快捷键提交（Ctrl + Enter）  
✅ **存储方式切换**：「写入日记」或「时间戳笔记」  
✅ **格式切换**：「任务列表」或「普通笔记」  
✅ **自动归档**：笔记会智能存入相应的文件和章节, 无需手动整理  

### **TasksView（笔记筛选模块）**

✅ **4 大核心筛选**：「任务」、「列表」、「日记」、「闪念」  
✅ **高级筛选**：支持 **日期范围** 和 **标签匹配**  
✅ **即时更新**：无需刷新, 点击按钮立即筛选笔记  

## **适用场景**

- **GTD 任务管理**：记录待办事项, 自动存入任务列表  
- **日记回顾**：写入每日笔记, 自动分类存入“想法”或“计划”部分  
- **灵感整理**：零散记录, 写入时间戳笔记, 自动归档  
- **时间线管理**：结合筛选功能, 按时间或标签快速回顾笔记  

## **文件结构**

**默认支持以下目录结构, 可在 YAML 头部自定义：**

📁 **日记**：`Mindscape/Diary/{年份文件夹(自动生成)}/YYYY-MM-DD.md`  
📁 **时间戳笔记**：`data/timestamp/`  
📁 **笔记类型划分**：日记文件内自动分为“想法”和“计划”部分  

## **为什么选择「MemoFlow」？**

🆚 **与传统笔记管理方式的对比**

✅ **自动记录 & 智能筛选**  
✅ **无需手动整理, 笔记自动归档**  
✅ **无需 Dataview 代码, 按钮筛选更直观**  
✅ **即时筛选, 无需刷新, 交互流畅**  

相比于手动管理笔记, 「MemoFlow」减少了繁琐的整理工作, 提高了笔记录入和筛选的效率。只需将代码复制到 Obsidian, 即可享受更智能的笔记管理体验！

## **使用方法**

### **1. 单文件使用**

1. **下载代码**：下载 `-MemoFlow-.md` 文件
2. **粘贴代码**：复制到 Obsidian 中
3. **设置路径**（可选）：根据需要修改 YAML 配置, 例如存储路径和日记插入位置等。
4. **开启dataviewjs**：安装dataview插件, 开启dataviewjs
5. **保存 & 运行**：保存代码后即可使用。

### 2. **在dataviewjs中引用js脚本**
可以下载单独的JavaScript文件(MemoFlowTasksView.js), 在markdown文档中使用以下dataviewjs语句引用上述脚本, 自动查找路径. 
```dataviewjs 
dv.view("MemoFlowTasksView") ;
```
这个方法暂时只支持TasksView模块, MemoInput暂时不支持, 原因未知

## **自定义YAML头文件参数说明**

**「MemoFlow」的行为可以通过 YAML 头文件自定义，以下是所有可用参数及其作用：**

| 参数名称             | 默认值                  | 作用说明 |
|---------------------|----------------------|--------|
| `DefaultToDiary`   | `true`（写入日记）       | 是否将笔记写入日记（`true`）或时间戳笔记（`false`） |
| `DefaultAsTask`    | `false`（普通笔记）      | 选择记录的格式：`true` 为任务列表（☑️），`false` 为普通笔记（🔘） |
| `PathToTimestamp`  | `data/timestamp`     | 记录时间戳笔记的存储路径 |
| `PathToDiary`      | `Mindscape/Diary`    | 记录日记的存储路径，日记会自动归档到 `PathToDiary/{年份}/YYYY-MM-DD.md` |
| `PosToDiaryList`   | `"想法"`               | 在日记中存放普通笔记的部分（默认是“想法”） |
| `PosToDiaryTask`   | `"计划"`               | 在日记中存放任务列表的部分（默认是“计划”） |
| `LimitNum`         | `64`                 | 笔记筛选的最大数量 |

**示例 YAML 配置：**

```yaml
---
DefaultToDiary: true      # 默认写入日记
DefaultAsTask: false      # 记录为普通笔记（不是任务）
PathToTimestamp: data/timestamp
PathToDiary: Mindscape/Diary
PosToDiaryList: 想法
PosToDiaryTask: 计划
LimitNum: 64
---
```

### **快速开始**

- **录入笔记**：输入内容, 选择存储方式（日记或时间戳笔记）, 点击提交。
- **筛选笔记**：使用任务、日记、闪念筛选按钮, 快速查看相关记录。


## **立即体验！**

📌 **让你的 Obsidian 更智能、更高效！**


