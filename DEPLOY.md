# GitHub Pages 部署手册

本文档将指导您如何将此项目部署为 GitHub Pages 静态网站。

我们使用 [Docsify](https://docsify.js.org/#/zh-cn/) 进行部署，它无需复杂的构建过程，能直接将您的 Markdown 文件渲染成一个美观、带侧边栏的文档网站。

部署所需的文件 (`index.html`, `_sidebar.md`, `.nojekyll`) 已为您准备就绪。

## 部署步骤

### 第一步：创建 GitHub 仓库

1.  在 GitHub 上创建一个新的**公开**仓库。
2.  获取仓库的 SSH 或 HTTPS 地址，例如 `git@github.com:your-username/your-repo.git`。

### 第二步：关联本地仓库并推送文件

在您的项目根目录（`/Users/hidetoshidekisugi/Documents/Work Out Plan`）下，执行以下命令：

```bash
# 初始化 Git 仓库（如果尚未初始化）
git init

# 切换到 main 分支（GitHub 的默认分支）
git branch -M main

# 添加所有文件到暂存区
git add .

# 提交更改
git commit -m "Initial commit with workout plan and docsify setup"

# 关联到你的 GitHub 远程仓库
# 将 your-github-repo-url 替换为你的仓库地址
git remote add origin git@github.com:your-username/your-repo.git

# 推送到 GitHub 的 main 分支
git push -u origin main
```

### 第三步：在 GitHub 上启用 Pages

1.  打开您在 GitHub 上的项目主页。
2.  点击顶部导航栏的 “Settings”。
3.  在左侧菜单中，选择 “Pages”。
4.  在 “Build and deployment” 部分，将 Source 设置为 “Deploy from a branch”。
5.  在 “Branch” 部分，选择 `main` 分支和 `/(root)` 目录。
6.  点击 “Save”。

GitHub Pages 服务启动后，会提供一个网址，例如 `https://your-username.github.io/your-repo`。几分钟后，访问该网址，您就可以看到您的在线健身计划文档了。

## 如何更新网站内容

之后，每当您修改了任何 `.md` 文件，只需执行以下命令即可将更新同步到网站：

```bash
# 添加更改
git add .

# 提交更改
git commit -m "更新了 xxx 训练计划"

# 推送到 GitHub
git push
```

GitHub Pages 会自动重新部署，通常一两分钟内您的网站就会显示最新内容。