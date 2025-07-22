# GitHub Pages 部署手册

本文档将指导您如何将此项目部署为 GitHub Pages 静态网站。

我们使用 [MkDocs](https://www.mkdocs.org/) 和 [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) 主题，并通过 **GitHub Actions** 实现自动化部署。

## 部署流程

本项目的部署是**完全自动化**的。您只需要将更改推送到 `main` 分支，GitHub Actions 就会自动为您完成网站的构建和发布。

### 第一步：推送现有更改

我们已经将项目切换为 MkDocs，并配置好了 GitHub Actions 自动化部署。现在，您只需将这些更改提交并推送到 GitHub 即可。

在您的项目根目录 (`/Users/hidetoshidekisugi/Documents/Work Out Plan`) 下，执行以下命令：

```bash
# 添加所有更改到暂存区
git add .

# 提交所有更改
git commit -m "feat: Migrate to MkDocs with GitHub Actions deployment"

# 推送到 GitHub 的 main 分支
git push
```

### 第二步：在 GitHub 上启用 Pages

推送代码后，GitHub Actions 会自动运行，并创建一个名为 `gh-pages` 的新分支，其中包含了构建好的静态网站文件。

您需要配置 GitHub Pages 来使用这个分支：

1.  打开您在 GitHub 上的项目主页。
2.  点击顶部导航栏的 “Settings”。
3.  在左侧菜单中，选择 “Pages”。
4.  在 “Build and deployment” 部分，将 Source 设置为 “Deploy from a branch”。
5.  在 “Branch” 部分，选择 `gh-pages` 分支和 `/(root)` 目录。
6.  点击 “Save”。

GitHub Pages 服务启动后，会提供一个网址，例如 `https://your-username.github.io/your-repo`。几分钟后，访问该网址，您就可以看到您的在线健身计划文档了。

**注意**：这个设置步骤只需要做一次。

## 如何更新网站内容

之后，每当您修改了 `docs/` 目录下的任何 `.md` 文件，只需将这些更改推送到 `main` 分支即可：

```bash
# 添加更改
git add .

# 提交更改
git commit -m "更新了 xxx 训练计划"

# 推送到 GitHub
git push
```

GitHub Actions 会自动检测到新的提交，并重新构建和部署您的网站。通常一两分钟内，您的网站就会显示最新内容。
