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


