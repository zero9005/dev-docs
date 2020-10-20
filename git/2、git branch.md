# 2、git branch

- `git branch <branchName>` 新建分支
- `git branch` 查看所有分支
- `git branch -v` 查看所有分支以及最后一次提交
- `git branch --merged` 查看已经合并到当前分支的分支
- `git branch --no-merged` 查看尚未合并到当前分支的分支
- `git branch -d xxx` 删除分支`xxx`，如果没全合并，则删除失败
- `git branch -D xxx` 不管是否全合并，都强制删除分支`xxx`
- `git checkout <branchName>` 切换分支
- `git checkout -b <branchName>` 新建分支并切换
- `git push --set-upstream origin <branchName>` 在远程主机建立分支<branchName>
- `git fetch origin`  更新远程分支
- `git remote update origin --prune `  更新远程的分支到本地，可用`checkout`切换
- `git merge <branchName>`合并其它分支到当前分支

