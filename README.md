# 链接管理器

基于 GitHub Pages 的个人链接收藏工具，支持分类浏览、增删改查，数据存储在仓库中的 `links.csv` (仅三列) 和 `.timestamps.json` 中。

## 部署步骤

1. 创建仓库 `wwff3170-debug/link-manager`
2. 将本目录所有文件推送到仓库
3. 在仓库 Settings -> Pages 中，选择 `main` 分支作为发布源
4. 访问 `https://wwff3170-debug.github.io/link-manager`

## 管理员功能

- 点击右上角「管理员」
- 输入你的 GitHub Personal Access Token (需勾选 `repo` 或 `public_repo` 权限)
- 验证通过后即可添加、编辑、删除链接
- 修改时间自动记录，不会出现在 CSV 中，而是存储在 `.timestamps.json`

## 文件说明

- `index.html` : 主页面，包含所有逻辑
- `links.csv` : 只存储 名称, URL, 类别 三列
- `.timestamps.json` : 存储每个链接的修改时间 (以 "名称|URL" 为键)
