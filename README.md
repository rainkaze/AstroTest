# AstroTest

这是一个基于 [Astro](https://astro.build/) 的学习项目，用来练习 Astro 的页面路由、Markdown 博客文章和基础站点结构。

目前已经部署在了 [https://rainkaze-test.netlify.app/](https://rainkaze-test.netlify.app/)

## 项目简介

当前项目包含一个简单的个人站点雏形：

- 首页：站点入口页面。
- 关于页：展示个人信息、技能列表和 Astro 模板语法示例。
- 博客页：列出 Markdown 编写的文章。
- 文章页：通过 `src/pages/posts/` 下的 Markdown 文件自动生成独立路由。

这个项目适合作为 Astro 入门练习，也可以继续扩展成个人主页、学习笔记站点或轻量博客。

## 技术栈

- Astro 6
- Markdown 内容页
- Node.js 22.12 或更高版本
- Prettier 与 `prettier-plugin-astro`

## 项目结构

```text
/
├── public/
│   ├── favicon.ico
│   └── favicon.svg
├── src/
│   └── pages/
│       ├── index.astro
│       ├── about.astro
│       ├── blog.astro
│       └── posts/
│           ├── post-1.md
│           ├── post-2.md
│           └── post-3.md
├── astro.config.mjs
├── package.json
└── tsconfig.json
```

Astro 会把 `src/pages/` 目录中的 `.astro` 和 `.md` 文件自动转换为页面路由。例如：

- `src/pages/index.astro` 对应 `/`
- `src/pages/about.astro` 对应 `/about/`
- `src/pages/blog.astro` 对应 `/blog/`
- `src/pages/posts/post-1.md` 对应 `/posts/post-1/`

`public/` 目录用于存放静态资源，例如图标、图片和其他不需要构建处理的文件。

## 常用命令

所有命令都需要在项目根目录中执行。

| 命令                      | 说明                                                   |
| :------------------------ | :----------------------------------------------------- |
| `npm install`             | 安装项目依赖                                           |
| `npm run dev`             | 启动本地开发服务器，默认地址为 `http://localhost:4321` |
| `npm run build`           | 构建生产版本，输出到 `dist/` 目录                      |
| `npm run preview`         | 本地预览生产构建结果                                   |
| `npm run astro -- --help` | 查看 Astro CLI 帮助                                    |
| `npx prettier . --write`  | 手动格式化代码                                         |

## 开发说明

- 新增普通页面：在 `src/pages/` 中创建 `.astro` 文件。
- 新增博客文章：在 `src/pages/posts/` 中创建 `.md` 文件。
- 新增静态资源：把文件放入 `public/`，然后通过根路径引用，例如 `/favicon.svg`。
- 调整站点样式：可以先在单个 `.astro` 文件中编写局部样式，后续再提取为公共布局和组件。

## 后续可完善方向

- 提取公共导航栏，避免在多个页面重复编写链接。
- 新增统一布局组件，让页面标题、语言、导航和基础样式保持一致。
- 为博客文章生成自动列表，避免在 `blog.astro` 中手动维护文章链接。
- 修复页面中的中文编码显示问题，确保源码、终端和编辑器都使用 UTF-8。
- 增加更完整的页面样式，让站点更适合作为个人主页展示。
