## 常用命令

**配置**

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --list
```

**仓库操作**

```bash
git init                  # 初始化仓库
git clone <url>           # 克隆远程仓库
```

**文件管理**

```bash
git status                # 查看当前状态
git add <file>            # 添加文件到暂存区
git add .                 # 添加所有修改
git reset <file>          # 从暂存区移除
git rm <file>             # 删除文件并提交
```

**提交**

```bash
git commit -m "message"   # 提交
git commit --amend        # 修改上一次提交
```

**分支**

```bash
git branch                # 查看分支
git branch <name>         # 创建分支
git checkout <name>       # 切换分支
git switch <name>         # 切换分支（推荐）
git switch -c <name>      # 创建并切换
git merge <name>          # 合并分支
git branch -d <name>      # 删除分支
```

**远程**

```bash
git remote -v             # 查看远程
git remote add origin <url>
git push -u origin main   # 推送主分支并建立追踪
git push                  # 推送
git pull                  # 拉取并合并
git fetch                 # 拉取但不合并
```

**查看记录**

```bash
git log                   # 查看提交历史
git log --oneline --graph # 简洁图形化
git diff                  # 查看修改
git show <commit>         # 查看某次提交
```

**撤销与回滚**

```bash
git checkout -- <file>    # 撤销未暂存的修改
git restore <file>        # 撤销未暂存的修改（新用法）
git reset --hard <commit> # 回到指定提交
git revert <commit>       # 生成一次反向提交
```

## 普通开发流程

**1. 基于主分支创建新分支并切换**

```bash
git checkout main             # 切换到主分支
git pull origin main		  # 拉取最新
git switch -c feature/my-task # 切换到新分支
```

**2. 开发并提交代码**

```bash
git status               # 查看当前git仓库状态
git add .                # 暂存所有修改
git commit -m "实现功能 X" # 提交
```

**3. 推送分支到远程**

```bash
git push -u origin feature/my-task
```

**4. 在远程仓库发起 Pull Request (PR) / Merge Request (MR)**
 合并到 `main`、`master`  或 `develop`，**务必谨慎操作**

> 这一步通常在 GitHub/GitLab/Codeup 的 Web 页面完成

**5. 合并完成后，本地清理**

```bash
git checkout main
git pull origin main
git branch -d feature/my-task       # 删除本地分支
git push origin --delete feature/my-task  # 删除远程分支
```

## 分支命名规范

| 前缀       | 用途说明           |
| ---------- | ------------------ |
| feat/xxx   | 新功能             |
| fix/xxx    | 修 Bug             |
| ref/xxx    | 重构代码           |
| perf/xxx   | 性能优化           |
| opt/xxx    | 一般优化（非性能） |
| docs/xxx   | 文档调整           |
| test/xxx   | 测试               |
| build/xxx  | 构建系统           |
| ci/xxx     | CI/CD              |
| rel/v1.2.3 | 发布版本           |
| hotfix/xxx | 紧急热修           |