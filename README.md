# 暗盒图片库 Canister Library

海带索引图 FILM 的附属项目：一个纯静态的胶片暗盒参考图集。访客无需登录即可按**厂商、胶片类型（彩色负片 / 彩色反转片 / 黑白负片 / 黑白反转片 / 电影卷）、ISO 感光度、标签**等维度筛选浏览；维护者通过浏览器管理端自助上传、批量整理，全程零代码。

<p align="center">
  <a href="https://ohsobrkn.github.io/canister-library/">在线访问</a> ·
  <a href="https://ohsobrkn.github.io/film-index-generator/">返回海带索引图 FILM</a>
</p>

## 特性

- **免登录浏览**：多维组合筛选 + 关键词搜索，大图 lightbox 查看完整元数据，筛选条件可经 URL 分享
- **自助维护**：管理端 `admin.html` 支持批量上传（自动生成缩略图）、批量套用元数据、单张编辑、删除 / 隐藏 / 重新归类、字典与筛选维度自定义——每项操作都是网页点选
- **分类可扩展**：筛选维度由 `data/canisters.json` 中的定义表驱动，新增「画幅」「年代」等维度无需改代码
- **零后端**：图片与元数据全部存放在本 Git 仓库，GitHub Pages 静态发布；每次维护形成一个规整的 commit，Git 历史即变更日志

## 目录结构

```
├── index.html          访客浏览页
├── admin.html          管理端（浏览器本地运行）
├── styles.css          暗房主题样式
├── data/
│   └── canisters.json  全部元数据（维度定义 + 字典 + 条目）
├── images/
│   ├── original/       原图（无损保存）
│   └── thumb/          缩略图（上传时自动生成）
└── docs/
    └── maintenance.md  日常维护手册
```

## 数据格式

`data/canisters.json` 的 `dimensions` 数组定义筛选维度（类型支持 dict 字典 / enum 枚举 / number 数值 / tags 标签），`dicts` 存字典值，`items` 存每张图片的元数据。新增维度后，管理端表单与公开页筛选器自动生效。

## 维护

请阅读 [docs/maintenance.md](docs/maintenance.md)：创建 fine-grained PAT、批量上传流程、修改 / 删除 / 隐藏条目、自定义维度、仓库体积监控与原图迁移 Release 存档的时机。

## 许可与致谢

本项目为 [海带索引图 FILM](https://github.com/ohsobrkn/film-index-generator) 的附属图库，基于 [Judian99/film-index-generator](https://github.com/Judian99/film-index-generator) 生态二创发展而来，感谢原作者开源。
