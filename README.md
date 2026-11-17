# cogx.run

> **万物皆插件，数据皆本地。** \
> _Plugin-Everything, Local-First._

CogX 官网源码：产品介绍、下载入口、Web 插件商店与文档中心。

[![Website](https://img.shields.io/badge/官网-cogx.run-blue?style=flat-square)](https://cogx.run)

---

## 技术栈

- **Astro**：全量静态输出，商店详情页构建时预渲染，列表与搜索在客户端完成
- **交互层**：页面以原生 HTML 为主，不绑定前端框架；需要 JS 的组件按需水合（`client:visible` 等），不整站打包

---

## 本地开发

前置环境：`node >= 26`、`pnpm >= 12`。

文档源文件不在本仓库内。首次启动前，先到本仓库的**上级目录**，把 文档 仓库克隆成兄弟目录，再回到本仓库安装依赖：

```bash
cd ..
git clone https://github.com/cogx-run/cogx_doc.git  # 当前项目不存在
cd cogx-website
pnpm install
pnpm dev
```

构建脚本会读取 `../cogx/docs`，复制到 `src/content/docs` 后生成页面。**找不到该目录会直接报错退出**，不会产出缺文档的残缺站点。

文档目录不在默认位置时，用环境变量指定：

```bash
# macOS / Linux
COGX_DOCS_DIR=/absolute/path/to/cogx/docs pnpm dev

# Windows PowerShell
$env:COGX_DOCS_DIR = "D:\path\to\cogx\docs"; pnpm dev
```

常用命令：

```bash
pnpm dev       # 本地开发
pnpm build     # 构建
pnpm preview   # 预览构建结果
```

---

## 部署

推送到 `main` 触发 GitHub Actions，构建完成后部署到 `cogx.run`。

站点只有这一个对外地址，不做多域名分发。

---

## 授权

- **代码授权**：[Apache-2.0](./LICENSE)，可自由修改、重新编译与分发
- **品牌与内容**：「CogX」名称、考格形象、Logo、产品文案与宣传素材不在开源范围内，保留所有权利。参考或复用代码时请替换为自己的品牌素材。
