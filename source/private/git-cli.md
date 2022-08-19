---
title: git-cli
date: 2022-08-15 15:23:51
tags:
---

### 关于版本控制

---

### 正常工作流

#### 初始配置

`git config`

- 配置用户名称与邮件地址
  ```bash
    git config --global user.name "John Doe"
    git config --global user.email johndoe@example.com
  ```
- 配置默认文本编辑器
  ```bash
    git config --global core.editor emacs
  ```
- 查看配置
  ```bash
    git config --list
  ```

#### 克隆/初始化仓库

`git clone`

- 协议
  - 本地协议（Local）
  - HTTP 协议
  - SSH（Secure Shell）协议
  - Git 协议

- 生成 SSH 公钥
  ```bash
    ssh-keygen -t rsa
  ```
  详情见[ssh key密钥生成与使用](./sshkeys.html)

`git init`

- config文件
  - `HEAD`  指示目前被检出的分支
  - `config` 包含项目特有的配置选项
  - `description` 仅供 GitWeb 程序使用
  - `hooks/` 包含客户端或服务端的钩子脚本（hook scripts）
  - `info/` 包含一个全局性排除（global exclude）文件
  - `objects/` 存储所有数据内容
  - `refs/` 存储指向数据（分支）的提交对象的指针
  - `index` 保存暂存区信息

#### 检查分支

git分支本质上仅仅是指向提交对象的可变指针，可向前向后自由移动，它会在每次的提交操作中自动向前移动。

- 查看分支
  `git branch`
- 新建分支
  `git branch 分支名`
- 切换分支
  `git checkout/switch`
- 删除本地分支
- `git branch -D|d`

#### 检查当前文件状态

`git status`

- 文件的三种状态
  - 已提交（committed）
  - 已修改（modified）
  - 已暂存（staged）

#### 查看内容修改前后更改

`git diff`

#### 跟踪新/已修改文件(修改内容添加到暂存区)

`git add`

多功能命令，跟踪新文件或将已跟踪文件放到暂存区，还能用于合并时把有冲突的文件标记为已解决状态，可理解为“添加内容到下一次提交中”

#### 记录对存储库的更改(提交)

`git commit`

- 常用参数
  - -m，本次提交简易说明
  - --amend -m，修改本次提交说明
  - -a，将修改且追踪的文件添加到暂存区，且记录

#### 拉取线上代码

`git pull`

多功能命令，将来自远程存储库的更改合并到当前分支中，等同于`git fetch && git merge`

#### 推送代码

`git push`

新分支推送时需关联上游分支

---

### 常用命令

#### 代码合并相关

合并分支
`git merge`

合并提交
`git cherry-pick`

变基
`git rebase`

快进合并&三方合并

#### commitId相关

查看历史提交
`git log`

#### 储藏

`git stash`

- 将修改储藏起来
  `git stash save`
- 查看储藏内容
  `git stash list`
- 应用某个储藏
  `git stash apply 储藏名`
- 删除某个储藏
  `git stash drop 储藏名`
- 删除所有储藏
  `git stash clear`


### 常用技巧

#### 合并多个commit为一个

#### worktree使用

#### contains使用
