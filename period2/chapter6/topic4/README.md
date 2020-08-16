git版本控制

# 回退操作

撤销工作区的修改：git checkout filename

撤销暂存区的修改：git reset filename

撤销本地仓库的修改：git reset --hard origin/master

撤销远程仓库的修改：git reset --hard HEAD^，然后执行git push -f


git commit --amend -m "add test container"