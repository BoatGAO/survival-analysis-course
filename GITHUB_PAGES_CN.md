# 上传 GitHub 并生成网页

本项目是纯静态英文网站，无需安装 Node.js、无需构建，也不需要付费服务器。

## 1. 新建仓库

登录 https://github.com ，点击右上角 **+ → New repository**。

- Repository name：建议 `survival-analysis-course`。
- 选择 **Public**。
- 点击 **Create repository**。

## 2. 上传文件

在仓库页面选择 **uploading an existing file**，或 **Add file → Upload files**。

将 `survival-course` 文件夹内的 `index.html`、`styles.css`、`app.js`、`chapters.js`、`README.md`、`GITHUB_PAGES_CN.md` 上传。`.nojekyll` 是隐藏文件，方便时一起上传；本项目即使没有它也可由 GitHub Pages 提供静态页面。

注意：上传文件夹里面的文件，确保仓库首页能直接看到 `index.html`，不要把它放在额外的 `survival-course/` 子目录下。不要上传工作区中的教材 PDF。压缩包需要先解压，不能只上传 ZIP。

填写提交说明，例如 `Add interactive survival analysis course`，点击 **Commit changes**。

## 3. 开启 GitHub Pages

进入仓库 **Settings → Pages**。

在 **Build and deployment** 中：

1. Source 选择 **Deploy from a branch**。
2. Branch 选择 **main**（如实际默认分支名不同，选上传文件所在分支）。
3. 文件夹选择 **/ (root)**。
4. 点击 **Save**。

等待部署完成。可在 **Actions** 查看 `pages build and deployment` 是否成功。Settings → Pages 会显示实际网站地址，通常是：

`https://你的用户名.github.io/survival-analysis-course/`

这是地址格式示例，不是本次已经上线的网址。若看到 404，检查部署是否完成、`index.html` 是否位于仓库根目录以及 Pages 分支配置。

## 4. 后续更新

修改网站文件后，在同一仓库重新上传并 Commit。GitHub Pages 会根据配置自动重新部署。修改正文主要编辑 `app.js`，章节目录主要编辑 `chapters.js`。仅把已写好入门正文和测验的章节标记为 `available: true`。

## 本地预览

双击 `index.html` 即可打开；也可在终端执行：

```bash
cd "/Users/boatgao/Desktop/BoatWorkSpace/Survival Analysis/survival-course"
python3 -m http.server 4173
```

访问 http://localhost:4173 。终端按 Ctrl+C 停止服务。浏览器记录学习进度，不会同步到其他设备。

官方文档：
- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
