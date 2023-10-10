# git note
![git](images/git-logo.png) 
> Git is a free and open source distributed version control system designed to handle
> everything from small to very large projects with speed and efficiency.

# Git outline
1. [**Git简介**](#1-Git简介) 

    - 什么是Git？
    - Git的优势与特点
    - 分布式版本控制系统与集中式版本控制系统的比较

2. [**Git基础设置**](#2-Git基础设置)

    - 安装Git
    - 配置用户名和邮箱
    - 其他基本配置

3. [**Git基本命令**](#3-git基本命令)

    - 初始化仓库：`git init`
    - 克隆仓库：`git clone`
    - 查看状态：`git status`
    - 添加更改：`git add`
    - 提交更改：`git commit`
    - 查看日志：`git log`

4. **分支管理**
    - 创建分支：`git branch`
    - 切换分支：`git checkout`
    - 合并分支：`git merge`
    - 删除分支：`git branch -d`
    - 查看所有分支：`git branch -a`

5. **远程仓库操作**
    - 添加远程仓库：`git remote add`
    - 获取远程更改：`git fetch`
    - 推送到远程：`git push`
    - 从远程拉取：`git pull`
    - 查看远程仓库：`git remote -v`

6. **高级特性**
    - 历史回滚：`git reset`
    - 使用 `git stash` 临时保存更改
    - 交互式rebase: `git rebase -i`
    - Cherry-pick 提取提交
    - 使用 `.gitignore` 忽略文件

7. **合作与团队工作流**
    - Fork 和 Pull Request
    - Feature Branch 工作流
    - Gitflow 工作流
    - Centralized Workflow

8. **常见问题与解决方法**
    - 解决合并冲突
    - 撤销错误操作
    - 找回误删的提交

9. **Git配合工具与服务**
    - 使用 GitHub/GitLab/Bitbucket
    - 图形化客户端推荐（如 SourceTree, GitKraken）
    - 配合CI/CD工具

10. **附录与推荐资源**
    - Git命令速查表
    - 推荐书籍与在线教程
    - 相关社区与论坛

## 1. Git简介
- 什么是Git？

    - Git是一个分布式版本控制系统，用于跟踪计算机文件的更改。
    - 由Linus Torvalds于2005年为Linux内核开发而创建。
    - 开源并免费。

- Git的优势与特点

    - 快速、可靠。
    - 支持非线性开发 (数千个并行的分支)。
    - 可以处理大项目。
    - 分布式系统允许多个开发者同时工作。

- 分布式与集中式的比较

    - 分布式（如Git）：每个开发者拥有仓库的完整副本。
    - 集中式（如SVN）：单一的中心化版本库，开发者只获取最新的快照。

## 2. Git基础设置

- 安装Git

    - **Linux**: sudo apt-get install git
    - **Mac**: brew install git
    - **Windows**: 下载并安装Git官方安装程序。

- 配置用户名和邮箱

    ```bash
        git config --global user.name "your name"
        git config --global user.email "your@email.com"
    ```

- 其他基本配置

    - 设置默认的文本编辑器（如vim）: git config --global core.editor vim
    - 查看当前配置: git config --list

## 3. Git基本命令

- 初始化仓库

    ```bash
        git init
    ```
- 克隆仓库

    ```bash
        git clone [url]
    ```
- 查看状态

    ```bash
        git status
    ```
- 添加更改

    ```bash
        git add [file or directory]
    ```
- 提交更改

    ```bash
        git commit -m "commit message"
    ```
- 查看日志

    ```bash
        git log
    ```
## 4. 分支管理

- 创建分支

    ```bash
        git branch [branch-name]
    ```
- 切换分支

    ```bash
        git checkout [branch-name]
    ```
- 合并分支

    ```bash
        git merge [branch-name]
    ```
- 删除分支

    ```bash
        git branch -d [branch-name]
    ```
- 查看所有分支

    ```bash
        git branch -a
    ```
## 5. 远程仓库操作

- 添加远程仓库

    ```bash
        git remote add [name] [url]
    ```

0 获取远程更改

    ```bash
        git fetch [remote-name]
    ```

- 推送到远程

    ```bash
        git push [remote-name] [branch-name]
    ```

- 从远程拉取

    ```bash
        git pull [remote-name] [branch-name]
    ```

- 查看远程仓库

    ```bash
        git remote -v
    ```

## 6. 高级特性

- 历史回滚

    ```bash
        git reset [commit]
    ```

- 使用 git stash 临时保存更改

    ``` bash
        git stash save "description"
    ```

- 交互式rebase

    ```bash
        git rebase -i [base-commit]
    ```

- Cherry-pick 提取提交

    ```bash
        git cherry-pick [commit]
    ```
- 使用 .gitignore 忽略文件

    - 在项目根目录下创建 .gitignore 文件。
    - 添加要忽略的文件或文件夹名。

## 7. 合作与团队工作流

- Fork 和 Pull Request

    - 在GitHub上对原始仓库进行fork。
    - 克隆fork的仓库到本地。
    - 创建一个新的分支进行更改。
    - 提交更改并推送到fork的仓库。
    - 在GitHub上提交一个pull request给原始仓库。

