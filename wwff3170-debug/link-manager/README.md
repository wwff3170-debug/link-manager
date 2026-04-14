# Link Manager 🔗

一个简洁高效的链接管理工具，支持分类存储、实时编辑和自动同步到 GitHub。

## ✨ 功能特性

- 📂 **分类管理** - 支持5个预设分类：毕业课题、AI学习、代码、实用工具、其他
- 🌐 **水平导航** - 直观的导航栏快速切换分类
- ✏️ **实时编辑** - 管理员可在网页中直接添加、编辑、删除链接
- 🔄 **自动同步** - 修改自动上传到仓库的 CSV 文件
- 📱 **响应式设计** - 适配各种设备屏幕
- 🚀 **GitHub Pages 托管** - 完全免费的静态网站

## 🎯 快速开始

### 本地开发

```bash
# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 访问 http://localhost:5173
```

### 构建与部署

```bash
# 构建项目
npm run build

# 预览构建结果
npm run preview
```

项目配置为自动部署到 GitHub Pages。每次 push 到 main 分支时，GitHub Actions 会自动构建并发布。

## 🔑 管理员使用

### 首次设置

1. 点击右上角 **管理员** ��钮
2. 输入管理员密码：`admin123`
3. 输入你的 GitHub 信息：
   - GitHub 用户名
   - 仓库名（link-manager）
   - Personal Access Token（需要 repo 权限）

### 获取 Personal Access Token

1. GitHub 设置 → Developer settings → Personal access tokens → Tokens (classic)
2. Generate new token，勾选 `repo` 权限
3. 复制并保存 token

### 操作指南

- **添加链接** - 点击"+ 添加新链接"
- **编辑链接** - 找到链接后点击"编辑"按钮
- **删除链接** - 找到链接后点击"删除"按钮
- **登出** - 点击"登出"清除本地认证信息

所有修改会自动上传到仓库的 `data/links.csv` 文件。

## 📊 数据格式

CSV 文件格式（data/links.csv）：

```csv
name,category,url,modifiedAt
链接名称,code,https://example.com,2026-04-14
```

**字段说明：**
- `name` - 链接显示名称
- `category` - 分类（graduation|ai|code|tools|other）
- `url` - 链接地址
- `modifiedAt` - 最后修改日期（YYYY-MM-DD）

## 🏗️ 技术栈

- **前端框架** - React 18 + TypeScript
- **构建工具** - Vite
- **样式** - Tailwind CSS
- **GitHub 集成** - Octokit.js
- **CSV 解析** - PapaParse
- **托管** - GitHub Pages

## 📁 项目结构

```
link-manager/
├── src/
│   ├── components/
│   │   ├── Navigation.tsx      # 导航栏
│   │   ├── LinkList.tsx        # 链接列表
│   │   ├── LinkForm.tsx        # 链接表单
│   │   └── AdminPanel.tsx      # 管理面板
│   ├── services/
│   │   ├── githubService.ts    # GitHub API 服务
│   │   └── csvParser.ts        # CSV 解析器
│   ├── utils/
│   │   └── auth.ts             # 认证工具
│   ├── types/
│   │   └── index.ts            # TypeScript 类型
│   ├── App.tsx                 # 主组件
│   └── main.tsx                # 入口文件
├── public/
│   └── index.html              # HTML 模板
├── data/
│   └── links.csv               # 链接数据
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions 配置
└── package.json
```

## 🔐 安全说明

- 管理员密码和 Token 仅存储在浏览器本地存储中
- 不建议在公共电脑上使用
- Token 具有仓库完整权限，请妥善保管
- 建议定期轮换 Token

## 🌐 访问网站

项目部署后访问：`https://wwff3170-debug.github.io/link-manager/`

## 📝 许可证

MIT