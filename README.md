# 橄榄与火 · 西餐宣传网页

这是一个简单的静态宣传网页项目，页面文件为 `index.html`，无需安装依赖即可在浏览器中打开。

## GitHub 仓库页面说明

下面按你提供的 GitHub 页面截图，从上到下说明各区域的作用：

### 页面顶部导航

- **`zhangxingda25 / codex-researching`**：仓库所属账户和仓库名称。点击仓库名可回到项目主页。
- **Code**：查看项目文件、分支和提交记录，也是当前截图所在的页面。
- **Issues**：记录问题、缺陷和待办事项。
- **Pull requests**：查看或讨论准备合并的代码更改。
- **Actions**：查看自动化任务，例如自动构建或部署。
- **Projects**：用看板管理项目任务。
- **Wiki**：编写较详细的项目说明文档。
- **Security and quality**：查看安全与代码质量相关功能。
- **Insights**：查看提交、贡献者等仓库统计信息。
- **Settings**：管理仓库设置、访问权限和协作者等。账户级的 SSH 密钥不在这里，而在个人账户设置中。

### 仓库标题和协作按钮

- **`codex-researching`**：仓库名称。
- **Public**：仓库是公开的，任何人都可以浏览其内容。
- **Pin**：将仓库固定到个人主页。
- **Watch**：订阅仓库活动通知。
- **Fork**：在自己的账户下复制一份仓库。
- **Star**：收藏仓库。

### Copilot 和 Collaborators 卡片

- **Set up GitHub Copilot**：设置 GitHub 的编程辅助功能，可选，与当前网页项目能否运行无关。
- **Add collaborators to this repository**：邀请其他 GitHub 用户共同访问或维护仓库。

### Quick setup（浅蓝色区域）

这是新仓库的快速设置区，提供克隆或上传项目的入口。

- **HTTPS / SSH**：切换仓库地址的连接方式。HTTPS 通常通过浏览器登录或访问令牌认证；SSH 使用本机 SSH 私钥进行认证。
- **地址框**：当前显示的 `git@github.com:zhangxingda25/codex-researching.git` 是仓库的 **SSH 地址**，不是 SSH 密钥。
- **复制图标**：复制地址。
- **creating a new file**：直接在 GitHub 网页上新建文件。
- **uploading an existing file**：从电脑上传文件。
- **README、LICENSE、.gitignore**：GitHub 建议仓库可以包含的说明文档、授权许可和忽略规则文件。本项目已有 `.gitignore`，本说明文件就是 `README.md`。

### 命令行设置区

- **create a new repository on the command line**：适用于电脑上还没有本地仓库、准备从头创建的情况。
- **push an existing repository from the command line**：适用于电脑上已经有 Git 仓库、要把它推送到 GitHub 的情况。本项目属于这种情况。

本地项目已经有 `main` 分支和首次提交。改用 SSH 地址并推送时，命令大致如下：

```bash
git remote set-url origin git@github.com:zhangxingda25/codex-researching.git
git push -u origin main
```

## SSH 密钥在哪里

SSH 密钥由电脑上的一对文件组成：

- **私钥**：通常是 `~/.ssh/id_ed25519`。留在自己的电脑上，不能发给别人，也不能贴到 GitHub。
- **公钥**：通常是 `~/.ssh/id_ed25519.pub`。可以复制其内容添加到 GitHub。

在 GitHub 网页中，点击右上角头像 → **Settings** → 左侧 **SSH and GPG keys** → **New SSH key**。将电脑生成的 `.pub` 公钥内容粘贴到 **Key** 框中，填写标题后保存。此处添加的是公钥，不是截图中的仓库地址，也不是私钥。

如果电脑还没有这对密钥，需要先在终端生成。下面命令中的邮箱应替换成你 GitHub 账户使用的邮箱：

```bash
ssh-keygen -t ed25519 -C "你的GitHub邮箱"
```

按提示保存后，可用下面命令显示公钥，再复制输出内容到 GitHub 的 **Key** 框：

```bash
cat ~/.ssh/id_ed25519.pub
```

完成后可以测试 SSH 认证：

```bash
ssh -T git@github.com
```

认证成功后，再执行 `git push -u origin main` 推送本地提交。
