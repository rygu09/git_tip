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

本年度工作总结


渠道接入、打包调试
2018-09-17----2018-11-16 完成度：
100%
 
工作内容:

1、负责国内多个游戏不同渠道的接入，渠道版本更新和代码优化工作

2、打包和调试工作


遇到难点:


接入渠道出现问题时（比如闪退、初始化卡死等），通过日志排查解决相关问题

取得成绩:


完成了多个游戏、不同渠道sdk接入、更新工作



打包系统包体检测插件的开发与优化
2018-09-24----2018-10-21 完成度：
100%
 
工作内容:

1、制定包体检测插件检测方案、代码编写

2、配置jenkins构建脚本，部署检测插件

3、检测结果提交服务端

遇到难点:

插件的部署和post检测结果，需要熟悉jenkins构建和服务器交互相关流程

取得成绩:

1、成功开发检测插件并上线运行

2、方便在打包过程中对现有资源，如sdk.xml配置项，dex文件关键类等进行检测

3、在打包失败时通过打包系统显示若干项检测结果，使打包问题细节可视化，从而更有针对性地进行问题排查

中间层测试客户端的开发
2018-10-12----2018-11-09 完成度：
100%
 
工作内容:

针对中间层开发调试困难的问题，开发了中间层测试客户端。主要负责客户端架构、UI设计，功能实现以及代码优化工作。

遇到难点:

模拟游戏事件调用中间层代码，需要对参数进行正确配置。

取得成绩:

通过开发中间层测试客户端，极大简化了中间层代码调试工作，提升了开发效率。

SDK版本迭代维护、组件化及Kotlin版本重构
2018-11-09----2018-12-07 完成度：
100%
 
工作内容:

1、负责大陆版、国际版SDK的版本迭代及维护
2、负责Webview、Firebase等基础功能的组件化
3、负责实名制组件、大陆版SDK的Kotlin版本重构及优化

遇到难点:

SDK架构及业务逻辑的梳理

取得成绩:

1、优化了SDK功能、UI

2、实现了基础功能与业务代码的剥离，降低耦合和代码重用

3、Kotlin版本重构提高了SDK跨平台性


下年度工作计划

计划1：


计划内容：


参与SDK工程web动态化与热更新功能的实现

衡量标准：



1、完成所分配的SDK核心工程、组件工程的动态化语言开发

2、完成热更新相关功能开发，通过补丁修复线上代码


计划目标：



2019-01 负责调研React Native，在综合比较Weex、Flutter等方案后最终确定动态化开发方案

2019-04 对所分配组件进行动态化开发和优化

2019-05 参与热更新开发

2019-06 对所分配SDK核心工程进行开发和优化

2019-07 打包测试动态化后的SDK工程



计划2：


计划内容：


参与SDK工程Kotlin版本构建

衡量标准：



1、完成所分配SDK核心工程Kotlin版本构建

2、完成所分配组件工程Kotlin版本构建


计划目标：


将所分配的SDK Java工程切换为Kotlin工程，提升代码跨平台性


本年度工作评价

工作量（工作的饱和度） 

5.0 


工作质量 

5.0 


工作时效（工作效率，是否返工、延期） 

5.0 



制度规范遵守情况（公司的规章制度、部门的工作规范和工作流程） 

5.0 



对该员工本次总结的评价（评价员工以上填写内容和填写态度） 

5.0 

 
自我综合评价：
本人自入职以来，能够很快适应自身工作，融入团队。工作努力积极，严格按照规范制度进行开发。参与了本小组的多个项目任务，完善了SDK和打包系统。工作量充实，完成质

量和效率高。遇到问题时，能够细心排查，多途径解决bug。积极参加技术培训，虚心学习，增长了自身技能。能够将所学运用到工作中，提升了代码质量和编码效率。同时存在

一些不足之处，比如对于项目整体架构理解不够深刻全面，代码的鲁棒性有待提高等。本人会在今后的工作中加深对项目的理解，不断完善自身的知识体系，在技术之路上有所

突破和创新。  
  
上级评语：

继续努力，在明年更快提高自己的代码水平


大牛就在身边，多去看他们的代码，多看，多想，多问，凭你的基础，一定会有比较大的发展


工作努力认真，希望来年在代码设计上能有更大的提升，在部门中可以担任更多的事情。

申请人述职报告(工作总结)
