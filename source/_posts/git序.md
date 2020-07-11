---
title: Git序
categories:
  - TOOLS
tags:
  - git
  - tools
comments: false
date: 2018-04-25 21:05:47
updated: 2020-04-25 21:05:47
img:
---

### 配置设置
{% codeblock lang:sh %}
git config --list #查看git配置信息
git config user.name  #查看git用户名
git config user.email  #查看邮箱配置
git config --global user.name "username"  #全局配置用户名
git config --global user.email "email"  #全局配置邮箱
{% endcodeblock %}

### 清空git缓存
{% codeblock lang:sh %}
git rm -r --cached . #不删除本地文件  （git rm -r --f . 删除本地文件）
git add .
git commit -m 'update .gitignore'
{% endcodeblock %}

### 删除在git add中添加的文件
{% codeblock lang:sh %}
git reset HEAD file  
git rm –cached file  #删除暂存区的文件，工作区的不受影响
git rm --f file   #删除暂存区与工作区的文件
{% endcodeblock %}

### 更新忽略规则.gitignore
{% codeblock lang:sh %}
# .gitignore只能忽略那些原来没有被track的文件（Untracked Files）
# 更新规则生效步骤先把本地缓存删除（改变成未track状态），然后再提交：
git rm -r --cached .
git add .
git commit -m 'update .gitignore'
{% endcodeblock %}

### refusing to merge unrelated histories
{% codeblock lang:sh %}
# 拉取合并两个没有共同祖先的分支
git pull origin master --allow-unrelated-histories

# 先fetch之后再合并
git fetch origin master
git merge origin/master --allow-unrelated-histories
{% endcodeblock %}

### 放弃本地修改，强制拉取fetch更新
{% codeblock lang:sh %}
git fetch –all  #下载远程的库的内容不做合并
git reset –hard origin/master  #把HEAD指向master最新版本
{% endcodeblock %}

### 取回更新并合并
{% codeblock lang:sh %}
git pull #和git fetch的区别：git pull = git fetch + git merge

git pull --rebase # 相当于 git fetch + git rebase

# 设置rebase为pull时候默认执行的动作
git config --global pull.rebase true
{% endcodeblock %}

### 改变分支依赖
{% codeblock lang:sh %}
#将当前分支基于依赖分支
git rebase 依赖分支 #对所有涉及的commit（"pick"）执行默认操作，将历史记录回滚到最后一个公共父节点，并重新生成两个分支的commit。
{% endcodeblock %}

### failed to push some refs to git
{% codeblock lang:sh %}
# 远程库中部分文件件不在本地库中造成冲突
git pull --rebase origin master
或
git push -u origin master -f
{% endcodeblock %}

### Untracked working tree file 'xxx' would be overwritten by merge
{% codeblock lang:sh %}
# 需要执行下面的命令才能修复：
git reset --hard HEAD    
git clean -f -d    
git pull  
{% endcodeblock %}

### 解决冲突文件
{% codeblock lang:sh %}
# 远程库文件覆盖本地文件
git pull
git checkout file

# 暂存本地修改后拉取最新文件
git stash
git pull
git stash list  #查看暂存记录列表
git stash apply stash@{0}
# 冲突文件修改
git commit 
git push

# 本地提交冲突文件commit后拉取最新文件
git add file
git commit
git pull
# 冲突文件修改
git commit
git push

# 使用rebase情况下，完成冲突解决
git rebase --continue

git rebase --skip #忽略此次提交
{% endcodeblock %}

### 修改commit注释
{% codeblock lang:sh %}
# 查看提交的信息
git show

# 修改最近一次的提交
git commit --amend #--amend会将更改添加到最近一个提交中

# 修改最近n次提交历史(合并多次提交或拆分提交)
git rebase -i HEAD~n  # -i表示用交互式打开

{% endcodeblock %}

### 撤销commit
{% codeblock lang:sh %}
git reset --soft HEAD^  #不删除工作空间改动代码，撤销commit，不撤销git add . 
git reset --soft HEAD~1 #同上
git reset --soft HEAD~2 #撤销近两次commit
git reset --mixed HEAD^ #同git reset HEAD^ 效果是一样的
git reset --hard HEAD^  #删除工作空间改动代码，撤销commit，撤销git add . 
{% endcodeblock %}

### 还原到某一版本
{% codeblock lang:sh %}
git tag backup_commit  #备份当前的分支到backup_commit
git push origin backup_commit
git reset --hard commit_id
git push origin branch -f
{% endcodeblock %}

### 删除commit
{% codeblock lang:sh %}
git reset --hard commit_id
git push origin HEAD --force
{% endcodeblock %}

### 恢复已删除commit
{% codeblock lang:sh %}
git reflog  #查看带hash值的历史操作，记录了某分支的每次操作
git reset --hard hash
{% endcodeblock %}

### 查询文件中每一行代码的 commit ID、提交者和提交日期
{% codeblock lang:sh %}
git blame filename
{% endcodeblock %}

### 从其它分支抓取指定commit合入当前分支中
{% codeblock lang:sh %}
git cherry-pick -x commit_id
{% endcodeblock %}


