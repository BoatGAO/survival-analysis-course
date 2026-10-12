# 更新 GitHub 与线上课程

## 本次更新

- README 重写：项目介绍、线上入口、章节覆盖、交互功能、使用方法、目录结构和维护说明。
- 第 1–3 章：全部 34 个教材小节的原创英文学习笔记，约 9,000 英文词，包含概念、公式条件、案例、理论说明和原创新练习。
- 新增章节内跳转、掌握程度清单、竞争风险实验和似然贡献实验。
- 第 4 章维持入门内容与 KM 实验；第 5–13 章维持待补充目录。

教材正文、图片、原始数据表与完整习题集不随网站上传。逐节覆盖清单见 `content/COVERAGE.md`。

## 1. 进入已连接 GitHub 的本地目录

在 VS Code 终端执行：

```bash
cd "/Users/boatgao/Desktop/BoatWorkSpace/Survival Analysis/survival-course-github"
git status
```

本次修改已写入这个文件夹。无需重新解压旧 ZIP；旧压缩包不含本次更新。

## 2. 提交并上传

按顺序执行：

```bash
git add index.html styles.css app.js chapters.js content README.md GITHUB_PAGES_CN.md UPDATE_GITHUB_CN.md .nojekyll .gitignore
git commit -m "Expand Chapters 1-3 and document the live course"
git -c http.version=HTTP/1.1 pull --rebase origin main
git -c http.version=HTTP/1.1 push origin main
```

执行每一条后先检查是否成功。发生错误就停在该步骤，不要继续下一条。`pull --rebase` 会先整合可能在网页上做过的远程修改；HTTP/1.1 用于避开此前遇到的 HTTP/2 framing error。无需再次 `git init` 或 `git remote add`。

如果 commit 提示 `nothing to commit`，说明改动可能已被提交，继续检查 `git status` 后执行 pull 和 push。

如果 pull 报冲突，按照终端标出的文件解决冲突，执行 `git add <解决后的文件>` 和 `git rebase --continue`。不要用 `push --force`。不确定时把错误发给我。

## 3. 等待自动部署

1. 打开 https://github.com/BoatGAO/survival-analysis-course/actions 。
2. 查看本次推送后的 `pages build and deployment`。
3. 等它显示绿色 ✓。
4. 打开 https://boatgao.github.io/survival-analysis-course/ 。
5. 按 `⌘ + Shift + R` 强制刷新。

Pages 来源继续使用 `main` 和 `/ (root)`，本次不需要调整设置或手动创建新工作流。

## 4. 检查新版本

- 首页显示 3 个详细章节和 5 个交互实验。
- 第 1 章有 1.1–1.19 全部内容。
- 第 2 章有 2.1–2.8，以及 Weibull 与竞争风险实验。
- 第 3 章有 3.1–3.7，以及删失时间线与似然贡献实验。
- 章节顶部的小节按钮可跳转，Practice 可展开解答，章节末尾可勾选知识点清单。
- 第 4 章计算器仍可修改输入并计算。

## 后续本地同步

如果换电脑或网页端改过文件，工作开始前先在干净工作区执行：

```bash
git -c http.version=HTTP/1.1 pull --rebase origin main
```

然后编辑、add、commit、push。详细笔记实际从 `content/course-notes.js` 加载；对应 `.md` 是阅读用导出，不会自动驱动网页。
