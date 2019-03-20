## Welcome to GitHub Pages

# java 关键字  
1.static   
https://www.cnblogs.com/dolphin0520/p/3799052.html  
2.final  
https://www.cnblogs.com/dolphin0520/p/3736238.html  

# java数据结构与算法  
1.java中常用的数据结构List，Set，Map等的区别与联系  
https://blog.csdn.net/qq_34337272/article/details/80294307  
2.树基本概念及二叉树（BinaryTree）的设计与实现  
https://blog.csdn.net/javazejian/article/details/53727333  
#java并发

1.java中synchronized关键字和ReentrantLock的区别：
相同点：两者都是可重入锁，在实现可重入性时，两者都是同一个线程没进入一次，锁的计数器都自增1，所以要等到锁的计数器下降为0时才能释放锁。

区别：
1.1 实现上：synchronized由jvm实现，而ReentrantLock由jdk实现
1.2 性能上：在jvm未对synchronized关键字做优化之前差ReentrantLock很多，但是synchronized引入偏向锁、轻量级锁、和自旋以后两者在性能上就差别不打了  
1.3 功能上：synchronized的实现更简单，加锁和解锁的工作由jvm来做，而ReentrantLock则需要用户手动的进行加锁和释放锁，为避免遗忘释放锁而造成阻塞在                finally语句中完成释放锁是不错的选择
1.4 ReenTrantLock独有的能力：ReentrantLock可以指定是非公平锁(默认)or公平锁，而synchronized只能是非公平锁。
                            ReenTrantLock提供了一个Condition（条件）类，用来实现分组唤醒需要唤醒的线程们，而不是像synchronized要么随机唤醒一个                             线程要么唤醒全部线程。
                            ReenTrantLock提供了一种能够中断等待锁的线程的机制，通过lock.lockInterruptibly()来实现这个机制。


**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/LHaisong/LHaisong.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

