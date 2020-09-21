## 首次配置 Git 用户信息

#### 全局配置(用户主目录生成配置文件，以后所有项目都读取改配置)
- `git config --global user.name 'yourName'`
- `git config --global user.email 'yourEmail'`

#### 单项目配置(新的设定配置保存在当前目录的 .git/config文件中)
- `git config user.name 'yourNmae'`
- `git config user.email 'yourEmail'`

#### 查看配置信息
- `git config --list`

## Git 工作流程
1. 克隆 Git 资源作为工作目录。
2. 在克隆的资源上添加或修改文件。
3. 如果其他人修改了，你剋更新资源。
4. 在提交前查看修改。
5. 提交修改。
6. 在修改完成后，如果发现错误，可以撤回提交并再次修改并提交。

## Git 工作区、暂存区、版本库

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

## Git 创建仓库
- `git init` / `git init dirName` 初始化仓库 / 指定 Git 仓库
- `git stauts -s` 查看状态 -s 显示简述
- `git add *.C` 添加暂存区或跟踪文件
- `git commit -m '注解'` 提交到版本库
- `git commit -am '注解'` 忽略添加暂存提交
- `git clone [url]` 从现有仓库克隆

## 分支操作 `[bName -> 分支名称]`
- 创建分支 : `git branch bName`
- 切换分支 : `git checkout bName`
- 创建并切换分支 : `git checkout -b bName`
- 合并分支 : `git merge`
- 列出分支 : `git branch`
- 删除分支 : `git branch -d bName`

## 查看提交历史
#### 常用的命令
- `git log` 查看历史提交记录
  - **选项**
    - `--oneline`: 查看历史记录简洁版
    - `--graph`: 查看历史记录并显示分支信息
    - `--reverse`: 反转顺序
    - `--author=aName`: 查看指定用户的提交记录
    - `--before={3.weeks.ago} --after={2010-04-18}` 查看某个区间的历史记录
    - `--no-merges` 隐藏合并提交

- `git blame <file>` 以列表形式查看指定文件的历史修改记录

## git 标签
- `git tag -a 标记信息` 给提交做特殊标记
- `git tag -a 标记信息 id` 给某次已提交的版本做标记 

## SSH 配置验证信息
- ssh-keygen -t rsa -C 'yourEmail@xxx.com'

## Git 操作远程库
#### 生成 SSH Key
1. `ssh-keygen -t rsa -C 'yourEmail` 生成 SSH Key
2. 将 `HOME` 目录下 `.ssh/id_rsa.pub` 里面的 key 复制
3. 将 key 粘贴到 github 账号上
4. `ssh -T yourEmail` 验证 key 是否添加成功

#### 关联远程仓库
1. 在 github 上创建仓库
2. 本地创建目录，初始化为仓库
3. 关联远程仓库: `git remote add origin [url]`
4. 查看当前远程库: `git remote -v`
5. 提取远程仓库到本地某个分支: `git fetch origin` + `git merge origin/master`
6. 推送消息到远程的某个分支: `git push -u origin master`
7. 删除仓库: `git remote rm origin2`

GIT 无法跟踪空目录，只会跟踪有修改的文件.
