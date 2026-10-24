# 如何发布到 GitHub

只上传本目录内的文件。不要上传它所在的上层工作区、其他输出文件夹、原应用源码压缩包或以前的 Git 历史。这里没有安装包，也不需要读者授予你手机权限。

## 网页上传

1. 登录自己的 GitHub，创建一个新仓库，例如 `local-focus-blueprint`。可以先设为 Private，检查内容后再决定是否公开。
2. 新建仓库时添加一个临时 README，进入仓库后选择 **Add file → Upload files**。
3. 把本目录里的 `README.md`、`PUBLISHING.md`、`skills/` 文件夹拖进去，确认目录层级被保留。这里只需这几份文本文件，不必上传整个 ZIP。
4. 手动添加本目录的 `.gitignore`，或在文件选择器显示隐藏文件后一起上传；网页上传不会按 `.gitignore` 帮你筛选文件。
5. 查看待提交文件列表，确认没有个人数据、密钥或安装包，再提交。
6. 打开仓库首页检查 README 的链接、Skill 的引用文件及内容。决定发布许可，最后再选择是否改为 Public。

GitHub 当前网页流程见官方说明：[创建仓库](https://docs.github.com/en/get-started/start-your-journey/creating-a-repository-for-your-project-on-github)、[上传文件](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)。按钮名称可能随界面语言不同。

## 熟悉 Git 时

先把本目录复制到一个单独的新文件夹，再进入该文件夹。不要在包含其他项目的父目录初始化或直接推送已有历史。

```text
git init
git add README.md PUBLISHING.md .gitignore skills
git diff --cached --stat
git diff --cached
git commit -m "Add local focus app rebuild blueprint"
gh repo create local-focus-blueprint --private --source=. --push
```

这些命令仅供发布者自行执行，本草案准备过程没有执行创建远程仓库或推送。GitHub CLI 需要发布者自己的登录授权；不要把令牌、密码或验证码发给 AI。

公开后可以把仓库链接发给别人，并说明：先看 README，再让自己的 AI 阅读 Skill 和引用文档；生成的应用由读者自行审查、构建和授权。
