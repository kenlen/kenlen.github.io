.. title: The Pragmatic Programmer 阅读笔记
.. slug: books-review-the-pragmatic-programmer
.. date: 2012/01/19 13:56:27
.. tags: Book,OldBlog
.. link: 
.. description: 
.. type: text

这半个月来我一直在读The Pragmatic Programmer: From Journeyman to Master (以下简称TPP) 中文翻译过来就是程序员修炼之道,虽然TPP最早发行于1999年但是里面的观点一点都不过时,.这本书是我多年以来读过的最好的一本书之一, 有种相见恨晚的感觉, 边读边在想如果一年前, 两年前我碰到这本书会怎么样, 里面的70 个tips不都是我这几年工作学习中所不断遇到的问题吗和感悟的经验吗.

Andrew 和 David 通过70个Tips 来阐述如何让程序员变得卓有实效的专家.在这70个Tips里面前后呼应包含 短小精悍的例子娓娓道来.并配合一些练习(challenge) 让你进行深入的思考

下面列举3个我感触最深的tip来说

    Make Quality a Requirements Issue:Involve your users in determining the project’s real quality requirements.

使质量成为需求问题,尽早的让用户参与进项目开发的过程中来,得到他们的反馈, 让他们权衡利弊, 知道什么时候已经是足够好的软件, 知道什么时候该停止,在真实的世界里完美的东西并不存在.

    Don’t Gather Requirements – Dig for Them

不要收集需求, 要去挖掘需求: 需求分析其实是一个软件工程里面一个很重要的分支,在日常工作中也经常会碰到用户连自己的需求是什么,定义是什么就让你开发这开发那,其实如果按照他们第一次所说的内容去开发的话往往会面临用户直口否认前面的文档, 他们会说其实我说的是A 你没理解,作出了B来 或者会碰到某几种特殊的情况要考虑进去但是用户刚开始的时候并没有给你说可能他忘记了.往往这几种特殊的情况需要让你动辄去改架构或者改一大堆代码.. 所以引导用户,挖掘客户需求是非常重要的

    DRY–Don’t Repeat Yourself

系统中的每一项功能都必须具有单一、无歧义、权威的表示。与此不同的做法是在两个或更多地方表达同一事物。如果你改变其中一处，你必须记得改变其它各处。这不是你能否记住的问题，而是你何时忘记的问题. 以前在数据库里面我们经常会做了很多Dim表, 在不同的dim表里面有相同功能的flag. 有可能team 里面一个同事使用的是flag a 另外一个用了flag b, 某天flag b 实效了.那么用flag b的同事的系统估计就出错了.这违背了DRY原则. 接下去的时间里面我得对一些数据库Dim表进行重构.

这些tips 和另外的tips其实是一个前后呼应并不孤立存在.比如DRY,如果不遵循Make it Easy to Reuse让复用变的容易的话,很快我们就发现DRY原则就被打破

这是一本常读常新的书,时不时有空的话拿出来翻翻提醒自己那70个Tips, 当然些Tips不单单是指对程序员有用, 任何从事IT 行业的人的都应该读读,这么经典的书一定会带给你深深的思索,如果英语条件好的推荐使用原版,或者是蔡学镛的评注版,因为中文翻译有点不到位,读起来不顺.最后我是在kindle上面看完此书原版.