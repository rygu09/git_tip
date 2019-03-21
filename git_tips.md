### 工具 git bash
### 常用命令  

    pwd //查看当前路径  
    cd 用 ‘/’  
    ls //查看目录  
    git status //查看当前状态  

### 创建本地仓库并将其push到远程仓库

    git init  
    git add . /git add 文件名.扩展名  
    git commit -m "balabala"  
    git remote add origin git@github.com:rygu09/git_tip.git  
    git push -u origin master  

### clone远程仓库到本地
    先cd到要clone的目录，然后：
    git clone git@github.com:michaelliao/gitskills.git

### 版本回退
    git log 查看log日志  
    git reset --hard HEAD^  
    或者 git reflog 查看命令历史  
    git reset --hard 3628164

### 分支
    合并分支的时候，当前分支是其他分支合并上来的，
    要将br1 合并到 master 要先 checkout master
    转换到master分支，再merge  
    查看分支：git branch  
    创建分支：git branch <name>  
    切换分支：git checkout <name>  
    创建+切换分支：git checkout -b <name>  
    合并某分支到当前分支：git merge <name>  
    删除分支：git branch -d <name> 
    
### 遇到的一些问题解决方法

**1、commit 没有 -m 进入 vim界面**

输入i进入insert输入模式

按ESC，下方insert消失，输入： 再输入 wq  回车，退出vim界面

**2、fast-forwards**

git pull 后再 git push

3、[添加新的SSH Key](https://www.cnblogs.com/superGG1990/p/6844952.html)

[git官网](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)

https://datastudio.google.com/u/0/navigation/reporting   Google的数据分析工具
https://cloud.google.com/bigquery/
https://firebase.google.com/docs/analytics/
http://www.gcping.com/ google 检测当前网络到Google各个节点直接的ping延迟
https://locust.io/   一个开源的压测工具，可模拟百万的用户行为


Android产品研发（一）-->实用开发规范   https://blog.csdn.net/qq_23547831/article/details/51534013  
美团组件化  https://tech.meituan.com/2018/12/20/modular-event.html

美团猫眼电影android模块化实战--可能是最详细的模块化实战 https://www.jianshu.com/p/d372cc6802e5

git 
删除远程分支   git push origin --delete 1.1.9.0314
删除本地分支   git branch -d dev
查看远程分支   git branch -a

使用React全家桶搭建一个后台管理系统    https://www.cnblogs.com/MuYunyun/p/6843584.html

react新手demo——TodoList   https://www.jianshu.com/p/211ecf8ed34e

React Native与Android通信交互   https://blog.csdn.net/u013718120/article/details/55506238

