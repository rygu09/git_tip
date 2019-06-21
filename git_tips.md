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

import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;

public class Node {
    private int value;
    private Node next;

    public Node(int value, Node next) {
        this.value = value;
        this.next = next;
    }

    /**
     * 删除多余节点
     * @param head
     * @return
     */
    public static Node deleteDuplicates(Node head) {
        if (head == null || head.next == null) {
            return head;
        }
        head.next = deleteDuplicates(head.next);
        return head.value == head.next.value ? head.next : head;
    }

    /**
     * 删除多余节点
     * @param head
     * @return
     */
    public static Node deleteDulp2(Node head){
        HashMap<Integer,Integer> map = new HashMap<>();
        Node root = head;
        Node before = head;
        while (head!=null){
            if (map.containsKey(head.value)) {
                before.next =  head.next;
                head = head.next;
            }else {
                map.put(head.value,1);
                before = head;
                head = head.next;
            }
        }
        return root;
    }

    /**
     * 删除第n个节点
     * @param head
     * @param n
     * @return
     */
    public static Node removeNthFormEnd(Node head, int n) {
        Node fast = head;
        while (n-- > 0) {
            fast = fast.next;
        }
        Node slow = head;
        while (fast.next != null) {
            fast = fast.next;
            slow = slow.next;
        }
        slow.next = slow.next.next;
        return head;
    }


    /**
     * 链表翻转 打印
     * 头插法
     * 头插法：使用头插法可以得到一个逆序的链表。
     * 1->2->3，加入一个头节点head，只用于操作中转，不存储数据
     * 先把head->1，然后继续从2->3中取
     * 变为head->2->1，最后变为head->3->2->1，从head.next开始输出就可以了
     */
    public static List<Integer> printListFromTC(Node listNode) {
        //头插法构建逆序链表

        //新建一个头部节点，只用于中转，不存储值
        Node head = new Node(-1);
        //链表反转
        while (listNode != null) {
            Node temp = listNode.next;
            listNode.next = head.next;
            head.next = listNode;
            listNode = temp;
        }
        List<Integer> list = new ArrayList<>();
        //真正的值是从第一个节点开始
        head = head.next;
        while (head != null) {
            list.add(head.value);
            head = head.next;
        }
        return list;
    }


    public void get(Node node){
        Node head =new Node(-1);
        Node temp=node;
        while (node!=null){
            temp=node.next;
            node.next=head.next;
            head.next=node;
            node=temp;

        }
    }


    public Node(int value) {
        this.value = value;
    }

    public Node() {
    }

    /**
     * 尾部添加节点
     * @param node
     */
    public void addToTail(Node node){
        Node temp = this;
        while(temp.hasNext()){
            temp = temp.next;
        }
        temp.next = node;
    }

    /**
     * 头部添加节点
     * @param head
     * @param node
     */
    public void addToHead(Node head,Node node){
        node.next = head.next;
        head.next = node;
    }

    /**
     * 在某个节点后面添加节点
     * @param node
     * @return
     */
    public Node addToNext(Node node){
        node.next = this.next;
        this.next = node;
        return node;
    }

    @Override
    public String toString() {
        String val = Integer.toString(value);
        if(next != null){
            val = val.concat(" hasNext ");
            val = val.concat(next.toString());
        }
        return val;
    }

    public boolean hasNext(){
        return this.next == null ? false : true;
    }

}

Android工程师的“面试指南”
logo
你好，我是孙鹏飞。又到了传统的“金三银四”换工作的高峰期，在互联网寒冬下，抓住机会就显得尤为重要了。那作为Android工程师我们应该从哪些方面去准备呢？例如，不

太熟悉的技能要不要写在简历上、要复习哪些Android组件的知识、刷算法题目有没有用，可能在面试前你都会仔细考虑这些问题。下面我就结合自身的经验和理解，帮你梳理一

下关于简历、面试和算法方面需要准备的内容，分享一些我的心得体会。

简历
简历在面试过程会起到至关重要的作用，我们需要非常注意简历的撰写。

在面试的过程中，面试官通常会非常关注你简历中的工作经历、项目介绍、技能特长这三部分的内容，如果你面试的公司没有固定题目的话，那很多问题都会围绕你简历里这三

部分内容去问。这里需要注意的一点是相关技能的书写，首先你要让面试官明确你面试的定级是什么。很多时候一个职位对应了很多个职级，在投简历的时候，你的简历需要让

面试官给你一个比较明确的定级，否则面试过程会比较被动，也会影响面试官对你的判断。因此这部分的内容需要突出自己的特长，也要写一些现在公司相对关心的问题，比如

你对插件化、热修复、组件化、性能优化等很熟悉，就可以明确的写上，但如果不是很熟悉那么尽量不要去写。如果你对Android某部分内容很熟悉就可以写得相对详细一些，比

如你对Handler、Binder机制很熟悉，就可以写“熟悉Android常见机制，比如Handler、Binder机制等”。而看到你很熟悉这部分内容，面试官可能在问问题时一层层深入，因此

你肯定需要提前准备一下这部分内容如何讲解，基本可以从机制的优点、重点、难点三方面去说明。

关于项目介绍主要体现你在这个项目或者这个团队中的作用，突出自己的贡献和项目的难点。很多同学可能在公司一直做需求的开发，会觉得自己的项目经验没有亮点，难度也

没有那么大，会觉得在这部分内容上比较吃亏。其实每个需求下来的时候你肯定会对这个需求有一个自己的设计，在这个过程中你会考虑如何对现有代码的影响最小，如何快捷

清晰的实现功能，以及在开发过程中对组件、控件的封装，考虑如何优化性能，有没有新的技术可以帮助开发这个需求的…我想我们每个需求都是通过一系列的考量和设计后才

实施的，你可以回去翻一下自己的代码，然后考虑一下如何把你的这些设计和思考体现在简历上，同样也是个不错的说明。

面试
对于Android工程师来说，面试开始的时候都会问一些算法和Android、Java的基础知识。针对Java的基础知识，我建议你看一下《码出高效：Java 开发手册》《深入理解Java虚

拟机》《Java并发编程的艺术》这三本书。对于Android的面试题，大多都是跟系统原理有关的内容，但也有很多没有准确答案的问题，比如四大组件的原理这样的题目，需要你

从一个宏观的角度去解释一下四大组件，或者你也可以拆分开一个个去讲解。

在面试前你需要提前准备一下，避免回答问题的时候没有条理，导致面试官对你的逻辑思维能力和语言表达能力产生不好的判断。一些Android经常使用到的组件一定要理解清楚

，比如Handler.postDelay的机制、触摸事件机制、自定义View、如何计算View大小、容器控件如何对子控件进行布局、数据库基本操作、Binder机制、LMK机制等。还有面试官

也可能会问一些开源框架的原理，我建议你也要多了解一些优秀的网络框架、图片加载框架、日志记录框架、EventBus、AAC框架的原理。对于相对复杂的插件化和热修复来说，

热修复可以去看一下《深入探索Android热修复》这本书，插件化可以去看《Android插件化原理解析》这个系列的文章。还有性能优化，最近几年公司对性能优化关注很多，有

的同学可能做过专门的性能优化或者自己开发过一些工具总结过一些方法论，这样比较好答一些。但是大部分同学可能平时都在关注业务需求开发，性能优化的实战可能并不是

很多。我建议你可以从业务开发过程中找一些点来说，比如在做一些公共的业务组件时需要在启动时初始化，那么就需要注意初始化过程中的性能；又或者在做一个列表页面的

时候，在复杂的列表View下如何保证滑动性能。相信你在平时开发过程中都会有自己的思考，可以结合具体的情景讲出来。

面试的后面大多都会从项目入手，你需要在面试之前针对你的项目做详细的准备。比如面试官会让你介绍一下你的项目，你需要体现出这个项目的难点、你在项目中的贡献、项

目的具体实现等，有可能还会问到一些具体的细节，所以建议是实事求是去讲，但一定要对自己的模块非常清晰。除了技术面试以外，有时还有可能会考察一些软技能，比如面

试官会考察你跨部门协作能力、沟通能力、时间管理、任务分配和职业规划等。

面试更多的还是要靠平时的积累和临场的发挥，做总结是很重要的，因为很多内容不经常使用的话过一段时间之后就会忘掉，这样就会出现原本自己做过的东西，因为忘记了细

节，结果在面试过程中没法很好的展现出来。就比如插件化、热修复这样的技术，其实原理相对来说比较简单，但是在开发的过程中会遇到很多很多的坑，如果没有一些关键点

的文字记录，过一段时间之后可能就忘记了某段代码是用于什么目的。所以在做完一次需求之后尽量多总结项目中的难点，使用到的框架以及这个框架的原理，以及其中花费时

间最长的地方。另外Bug最多的地方也要做总结一下原因，这样在面试前就不用把代码再翻一遍，了解自己的项目细节就可以做到游刃有余了。

对于复习，首先要对自己做一次自我了解，我是通过画脑图来进行这个过程的，我会整体默想一遍大概的知识体系，画成类似下图。回想每个知识点可能考到的内容，记录下自

己模糊的地方，然后去看网上同学们总结的面试题，再对每个题目都做一下回答。这是一个迭代过程。在你预想的问题都可以回答上来的时候，就需要深入挖掘一下技术细节和

深度了，比如我工作中开发了一个PLT Hook工具，这个工具可能是我参考开源项目并封装修改过来的，但对其中的细节并没有很了解，这个时候你就要对这个开源项目所涉及的

内容做一次系统学习了。



另一方面是需要在面试过程中提高面试官对自己的级别评价，比如大部分人回答GC的问题都是按照《深入理解Java虚拟机》里的内容复述一遍，这种回答基本也是可以的。不过

毕竟Java虚拟机和Android虚拟机的GC还是有些差别的，如果自己阅读过Android虚拟机GC相关资料或者自己分析过源码的话，可以从Android虚拟机的角度解释GC，比如Android

虚拟机里MarkSweep算法的增量回收、并行回收等，后台GC和前台GC、VisitRoot的执行过程、GC的触发方式、TLAB的处理、ConcurrentGC的原理、堆的Trim过程、内存碎片的解

决、Reference的处理、finalize函数调用等展开讲。如果你对一个机制很熟悉的话，可以把话题引到这上面去，然后一层层对这个知识点深入讲解，这样可以提升面试官对你的

等级评价。

算法
算法是一定要复习的，在很多面试的过程中都会穿插算法题。面试的算法题一般不会很难，可以分为基础的数据结构，比如数组、链表、栈、队列、二叉树、堆的使用，这几种

常见的数据结构的基础操作一定要很熟悉，比如链表逆置、删除、获取第K个元素、判断是否有环等，二叉树翻转、深度遍历、层级遍历、求树深度、公共父节点等。另一种是常

见的搜索、排序算法，这两类算法出现频率很高，一定要知道它们常见的几种实现方式，比如排序方式有冒泡、快排、插入、归并、堆排序等。注意这里一定不要简单的去记忆

算法实现，因为面试的时候可能不会直接让你写出对应的算法，会出一些使用搜索或者排序算法来实现的题目，这类题目你可以去LeetCode上通过标签过滤出来。



另一部分的算法题可能集中在贪心、动态规划、分治算法、深搜广搜等，这一类的算法相对需要一些技巧性。但面试算法题通常不需要太多行代码就能完成，一般都是在几十行

内就能完成的，所以你可以优先去找一些经典题目来做，比如爬楼梯、最大子序和等。但也会有一些相对复杂的题目是几种算法结合在一起的，比如二叉树的最大路径和就是深

度搜索和动态规划一起使用的题目。除此之外，也可能会遇到通过其他问题引申出的一些算法题目，比如HashMap可能会引申出红黑树的实现等。这些都有可能需要准备，虽然它

可能不会成为你整个面试的一个绊脚石，但有可能成为你获取一个高评价的筹码。

“临时抱佛脚”对于算法的学习和积累作用不是很大，因此需要我们在平时繁忙的工作中抽出一些时间来复习，你也可以去LeetCode、LintCode上刷刷题。另外，虽然大部分面

试的算法题目都是LeetCode上的简单题目，但你同样也需要关注一些中等和困难难度的经典题目。

总结
今天我并没有涉及太多具体的面试题，更多侧重的如何准备面试，而面试的准备其实是在我们平时工作过程中一点一滴积累的，复习只是作为一种在面试前巩固知识的手段。复

习的过程主要是我们对知识点的整理和总结，你可以想一下在面试的时候可能会遇到的问题，以及该如何去表达。但是我想说，虽然“临时抱佛脚”的准备可能有时有用，但是

在短时间内靠“突击”是很难理解到某个知识点更加深度层次的内容，而且知识面的广度也是需要时间和经验去积累的。所以不管你是否需要面试，在平时工作过程中都需要多

思考、多训练、多总结，在有需要的时候可以厚积薄发。

最后，如果你也在准备面试，可以在留言区分享一下你的准备情况和面试心得。当然你也可以留下你遇到的面试问题，把它分享给其他同学。

欢迎你点击“请朋友读”，把今天的内容分享给好友，邀请他一起学习。我也为认真思考、积极分享的同学准备了丰厚的“学习加油礼包”，期待与你一起切磋进步哦。



背景介绍
技术选型
案例演示
总结

1 2 3 4 5

锁 并发
https://www.cnblogs.com/mingyao123/p/7424911.html


组件化 插件化
组件化
https://juejin.im/post/5c207bfaf265da61193bd861

链表算法
https://juejin.im/post/5d07aed85188252354279693#heading-11
https://juejin.im/post/5d067f4ee51d4577596486fb#heading-7

排序
https://juejin.im/post/5cff49e75188257a6b40de80




