# git

## 设置全局账号权限
> $ git config --global user.name "Your Name" <br>
> $ git config --global user.email "email@example.com"
>> 查看 设置信息 git config --global  --list

## git 初始化
> git init 
- 初始化一个本地的仓库
- 生成 .git 文件夹记录 本地文件夹所有项目变更

## 查看状态
> git status [-s]
- s 代表类型
- 查看本地仓储的状态

## 添加暂存区
> git add [file]
- 用于跟踪文件 git add . [/ --all] 跟踪当前所有文件夹
- 创建 .gitignore 把忽略清单写入，设置方便集中筛选 
- // 如果不add到暂存区，那就不会加入到commit中

## 版本提交
```shell
 git commit -m '第一次版本说明在此'
 将本地的变化提交到本地的仓库文件夹归档
```

## 回退 级别 1
```shell
 git checkout -- filename 
 ** 删除修改 仅仅是删除工作去修改：add或者commit之前的文件状态
 ** ##实际上是用 暂存区的 库中替换 工作区的文件##
 git reset HEAD file
 ** 把暂存区的修改撤销掉，放回工作区，文件【内容】不回退
```
## 回退版本 级别 2
```shell
 git reset --hard [HEAD^]版本回退 HEAD表示版本意思
 HEAD^ 表示是一个版本 HEAD^^ 表示上上版本... 简写 HEAD~n: 表示回退到那个版本
- 或者通过log得到六位 git reset --hard [123456];
```

## 删除
```shell
 git rm file 删除文件并从库中删除
 ** git checkout -- filename 可以撤销 cmd命令/人为删除 del fileName删除
 *** ##实际上是用 暂存区的 库中替换 工作区的文件##
```

## 分支 branch
 ```shell
 git branch 查看分支
 git branch newBranchName 新建基于master的分支
 git checkout branchName 切换分支
 >... git checkout -b branchName 相当于创建并切换分支
 git merge branchName 合并指定分支到当前分支
 git branch -d branchName 删除分支
 git branch -D branchName 强制删除分支
 ```

 ## 保存工作场景
 > git stash
 > <br> git stash pop 修复后 回到现场

 ## 标签管理 方便根据标签进行操作
 > git tag [`v1.0`] 查看、创建标签 v1.0 <br>
 > git tag [-a] [-m] `v0.9` `6224937` 对特定commitId补建标签<br>
 > ... -a 指定标签名 -m 指定说明文字 <br>
 > git tag -d `v1.0` 删除标签 <br>
 > git push origin `v1.0` 标签默认存储在本地，可以推送远程<br>
 > ... git push orgin --tags 一次推送所有标签到远程 <br>
 > 删除远程比较麻烦 删除 本地再 git push origin :refs/tags/v1.0 <br>
 > git show `v1.0` 显示对应标签的信息

## 查看文件修改内容
```shell
 git diff [fileName] 查看具体的修改内容
 对比版本与现在的文件差异
```

## 查看提交日志
```shell
 git log 查看提交日志 回退后看不到 最近的 commitID
 git reflog 查看每一次的命令 可以在回退文件后找到 commitId
```

# 远端控制

### 创建ssh key
> ssh-keygen -t rsa -C "876572465@qq.com" [git bash中用]

### 关联本地库 + 远程库
> git remote add origin [https:// .. branch]; origin 默认库名 <br>
> git remote rm origin 删除关联<br>
> git remote [-v] 查看远程库信息/ 详细 

### 推送 / 抓取 本地内容到远程库
> git push -u origin [master/ BranchName] <br>
> -u 会把本地 [master] 分支与远程关联, 关联后 可以省略-u <br>
> git pull origin master 抓取远程库 <br>
> git checkout -b branch-name origin/branch-name 在本地创建和远程分支对应分支 <br>
> ...如果多人提交冲突 需要先设置 分支关联 否则pull失败: `no tracking information` <br>
> ...git branch --set-upstream `branchName` origin/`branchName`

## fork pull request
+ 在GitHub上，可以任意Fork开源仓库；
+ 自己拥有Fork后的仓库的读写权限；
+ git clone ...
+ 可以推送pull request给官方仓库来贡献代码。

## 托管网页
- git branch [`gh-pages`] 名字固定

## hexo 使用
+ hexo init folderName 初始化一个文件加
+ cd folderName 进入文件夹
+ npm install 安装依赖包
+ hexo serve 启动服务器 默认 4000端口
+ hexo deploy 。。。