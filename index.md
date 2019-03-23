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
java并发

1.java中synchronized关键字和ReentrantLock的区别：
相同点：两者都是可重入锁，在实现可重入性时，两者都是同一个线程没进入一次，锁的计数器都自增1，所以要等到锁的计数器下降为0时才能释放锁。
        但是两者在可重入性的实现上不一样，ReentrantLock在请求获取锁时会进行一个判断，判断当前是否有线程持有锁，持有锁的线程是否是当前请求锁的线程  

区别：  
1.1 实现上：synchronized由jvm实现，而ReentrantLock由jdk实现  
1.2 性能上：在jvm未对synchronized关键字做优化之前差ReentrantLock很多，但是synchronized引入偏向锁、轻量级锁、和自旋以后两者在性能上就差别不大了   
1.3 功能上：synchronized的实现更简单，加锁和解锁的工作由jvm来做，而ReentrantLock则需要用户手动的进行加锁和释放锁，为避免遗忘释放锁而造成阻塞在                finally语句中完成释放锁是不错的选择  
1.4 ReenTrantLock独有的能力：  
    ReentrantLock可以指定是非公平锁(默认)or公平锁，而synchronized只能是非公平锁。  
    ReenTrantLock提供了一个Condition（条件）类，用来实现分组唤醒需要唤醒的线程们，而不是像synchronized要么随机唤醒一个                             线程要么唤醒全部线程。  
    ReenTrantLock提供了一种能够中断等待锁的线程的机制，通过lock.lockInterruptibly()来实现这个机制。 
1.5 Reentrantlock实现原理见mmpfiles.

2.AQS详谈
  队列同步器AbstractQueuedSynchronizr是用来构建锁或者其他同步组件的基础框架，它使用了一个int型成员变量来表示同步状态，通过FIFO队列来完成资源获取线  程的排队工作，同步器使用的方式是继承，子类通过继承同步器并实现其抽象方法来管理同步状态，详细如下：  
  https://www.cnblogs.com/waterystone/p/4920797.html
  
3.可重入性，及synchronized可重入的实现原理  
   可重入指的是一个线程在已经得到某个对象的锁时，在运行过程中再次请求该锁会成功。每个锁关联一个线程持有者和计数器，当计数器为0时表示该锁没有被任何线程持有，那么任何线程都可能获得该锁而调用相应的方法；当某一线程请求成功后，JVM会记下锁的持有线程，并且将计数器置为1；此时其它线程请求该锁，则必须等待；而该持有锁的线程如果再次请求这个锁，就可以再次拿到这个锁，同时计数器会递增；当线程退出同步代码块时，计数器会递减，如果计数器为0，则释放该锁。  

4.jvm对java原生锁(synchronized)做的优化：  
1.自旋锁：在线程请求锁时，如果已有线程占有当前请求的锁，请求的线程并不马上放弃处理器的执行时间，而是稍等一会看是否有线程很快就会释放锁，可以让线程做           一个忙循环(自旋),自旋锁默认情况下是关闭的，需要用虚拟机参数来开启。   
2.锁消除：  
3.锁粗化：如果连续的零碎操作需要对同一个对象加锁，将会把整个锁同步范围扩大到整个操作序列外部，减少频繁互斥同步带来的性能损耗。    
4.轻量级锁：在代码进入同步块的时候，如果此同步对象未被锁定，虚拟机会在当前线程的栈帧中建立一个名为锁记录(lock record)的空间，用于存储锁对象目前。              Mark Word拷贝(displaced mark word)，然后虚拟机将会使用CAS操作尝试将对象的Mark Word更新为指向lock record,如果这个操作成功则拥有了该对            象的锁，Mark Word的锁标志为将会变成00，如果操作失败，虚拟机会检查对象的Mark Word是否指向了当前线程的栈帧，是则重入，否则说明当前锁对象            已经被其他线程抢占了，如果有多个线程竞争同一个锁则轻量级锁将不在有效，转变为重量级锁，后面线程阻塞。  
5.偏向锁： 当线程第一次获取锁对象的时候，虚拟机会把对象头的标志位设为01，进入偏向模式，同时使用CAS操作将持有偏向锁的线程的ID记录在Mark Word中，如果           CAS操作成功，则以后持有偏向锁的线程进入这个锁相关的同步块时不用再进行任何操作，当有另外一个线程尝试获取这个锁时偏向模式结束，根据锁对象目           前是否处于锁定状态，撤销偏向后恢复到轻量级锁状态或者无锁状态。
            

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/LHaisong/LHaisong.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.














