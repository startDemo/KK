### 首次配置 Git 用户信息

#### 全局配置(用户主目录生成配置文件，以后所有项目都读取改配置)
- `git config --global user.name 'yourName'`
- `git config --global user.email 'yourEmail'`

#### 单项目配置(新的设定配置保存在当前目录的 .git/config文件中)
- `git config user.name 'yourNmae'`
- `git config user.email 'yourEmail'`

#### 查看配置信息
- `git config --list`

### Git 工作流程
1. 克隆 Git 资源作为工作目录。
2. 在克隆的资源上添加或修改文件。
3. 如果其他人修改了，你剋更新资源。
4. 在提交前查看修改。
5. 提交修改。
6. 在修改完成后，如果发现错误，可以撤回提交并再次修改并提交。

### Git 工作区、暂存区、版本库

#### Git 工作区、暂存区、版本库
- 工作区 : 在电脑上能看到的目录。
- 暂存区 : 英文叫 stage / index，一般存放在 .git/index 中，所以有时候也将它称为索引。
- 版本库 : Git 项目根目录下的 .git 就是版本库，它包含了暂存区。
- 对象库 : objects 对象库, 位于 .git/objects 目录下，包含了创建的对象及内容

#### 执行命令时发生的一些操作
- 执行 `git add` 命令时，暂存区目录树更新，同时工作区修改的文件内容被写入对象库中的一个新对象中，且暂存区的文件索引会记录这个对象的 ID
- 执行 `git commit` 命令时， 暂存区的目录树写到版本库(对象库)中，master 分支被更新, HEAD 指向暂存区提交的目录树
- 执行 `git reset HEAD` 命令时，暂存区重写为 master 分支指向的目录树，但工作区不受影响。
- 执行 `git rm --cached <file>` 命令时，暂存区文件被删除，工作区不做改变。
- 执行 `git checkout` 命令时， 会用暂存区的全部或指定文件替换工作区的文件，工作区未添加暂存区的改动会被清除。
- 执行 `git checkout HEAD` 命令时，会用 HEAD 指定的分支中的全部或指定文件替换暂存区和工作区的文件，这将清除工作区所有修改的文件及暂存区未提交的修改。

### Git 创建仓库
- `git init` / `git init dirName` 初始化仓库 / 指定 Git 仓库
- `git stauts -s` 查看状态 -s 显示简述
- `git add *.C` 添加暂存区或跟踪文件
- `git commit -m '注解'` 提交到版本库
- `git commit -am '注解'` 忽略添加暂存提交
- `git clone [url]` 从现有仓库克隆

### 分支操作 `[bName -> 分支名称]`
- 创建分支 : `git branch bName`
- 切换分支 : `git checkout bName`
- 创建并切换分支 : `git checkout -b bName`
- 合并分支 : `git merge`
- 列出分支 : `git branch`
- 删除分支 : `git branch -d bName`

### SSH 配置验证信息
- ssh-keygen -t rsa -C 'yourEmail@xxx.com'

### Git 操作远程库
- 关联远程库: `git remote add origin gitResitoryPath`
- 推送本地仓库内容: `git push -u origin master`
- 查看远程库: `git remote -v`
- 提取远程仓库
  1. 从远程下载新分支: `git fetch origin` + `git merge origin/master`
  2. 从远程提取数据并尝试合并到当前分支: `git pull`
- 推送分支到远程: `git push orgin master`
- 删除远程分支: `git remote rm [别名]`


