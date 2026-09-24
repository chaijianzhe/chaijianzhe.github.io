# Jianzhe Chai 的学术主页

采用简洁的 Academic Pages 风格：左侧个人资料、右侧学术内容。GitHub Pages 使用原生 Jekyll 自动生成网页；部署和日常更新无需安装 npm。

## 首次发布

1. 登录 [chaijianzhe](https://github.com/chaijianzhe)，新建公开仓库 **chaijianzhe.github.io**。若仓库已存在，先备份需要保留的文件。
2. 将本文件夹中的文件和目录上传到仓库根目录，保留 `_data`、`_layouts` 等目录结构。不要把外层 `chaijianzhe.github.io` 文件夹一并上传。
3. 打开仓库 **Settings → Pages → Build and deployment**，选择 **Deploy from a branch**，选择 **main** 分支和 **/ (root)** 目录，保存。
4. 等待 Pages 构建成功，再访问 [https://chaijianzhe.github.io/](https://chaijianzhe.github.io/)。本文件包本身不表示网站已经发布。

请勿添加 `.nojekyll` 文件：本网站需要 Jekyll 读取资料并生成页面。

## 以后只改一份资料文件

网页的个人资料、联系方式、研究方向、新闻、论文、教育经历、任职、报告和荣誉都放在 **`_data/profile.json`**。在 GitHub 上打开该文件，点击编辑，修改后提交到 `main` 分支；Pages 会重新生成网站。

- `name`、`biography`、`location`：姓名、简介段落和所在地。
- `email`、`github`、`dblp`、`lab`：侧栏联系方式和学术链接。`secondaryEmail` 保留备用邮箱，默认不显示。
- `roles`：侧栏只显示 `status` 为 `current` 的当前身份，顺序与列表一致；`completed` 的已结束经历不会显示在侧栏。身份变化时请同步更新简介、新闻与经历。
- `news`、`researchInterests`、`publications`：新闻、研究方向和论文。添加论文时复制一条已有记录，修改标题、作者、链接和 BibTeX；没有的链接可留空字符串。
- `education`、`appointments`、`presentations`、`honors`：对应各经历栏目。列表顺序就是网页上的显示顺序。
- `roles` 和 `appointments` 中的 `detail` 为研究组等补充信息；可选的 `detailUrl` 将这段文字链接到研究组官网，不需要链接时可省略或留空。
- `updated`：页面底部的更新日期。

JSON 的文字需要放在英文双引号内，项目之间使用逗号，最后一项后面不加逗号。换行使用 `\n`。固定栏目标题和布局位于 `_layouts/default.html`，样式位于 `styles.css`，日常资料更新无需编辑它们。

当前资料将博士生与 RIKEN Research Associate 作为当前身份展示，并保留 **2026 年 10 月开始博士阶段**、**2026 年 11 月开始 RIKEN Research Associate** 的日期。GitHub 账号为 [chaijianzhe](https://github.com/chaijianzhe)。发布前可检查侧栏的邮箱和个人链接。

## 添加自己的头像

目前使用中性的头像占位图。将真实头像上传为例如 `assets/avatar.jpg`，再把 `_data/profile.json` 的 `avatar` 改为 `"assets/avatar.jpg"`。将 `avatar` 留空会继续显示占位图。

## 本地预览

直接打开 **`preview.html`** 即可查看此次生成的页面。也可以在本目录打开终端，运行：

```sh
python3 -m http.server 8000
```

随后访问 [http://localhost:8000/preview.html](http://localhost:8000/preview.html)，按 `Ctrl+C` 停止。

`preview.html` 是本次导出的静态快照，编辑 JSON 不会自动更新它；它已从 Jekyll 发布内容中排除。线上页面由 Jekyll 根据 `_data/profile.json` 生成，因此提交资料修改后会更新。直接用浏览器打开 `index.html` 不会执行 Jekyll。

本文件包未包含原始 CV PDF。如需添加简历下载，请使用适合公开的版本。若换用其他 GitHub 账号或项目子目录，请同步调整 `_config.yml` 中的 `url`、`baseurl` 以及资料中的 `siteUrl`。
