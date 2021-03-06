## LAB4: 死锁

### 任务：
>1. 编写Deadlock.java程序
>2. 修改count值，使其运行时出现死锁
>3. 截图保存，并试着分析死锁出现的原因
>4. 理解死锁出现的条件

### 结果展示
>#### 死锁结果截图
>![](http://p1.bqimg.com/567571/89014ae7e3123e1b.jpg)


###产生死锁的四个条件
>1.互斥条件：一个资源每次只能被一个进程使用
>
>2.请求与保持条件：一个进程因请求资源而阻塞时，对已获得的资源保持不放
>
>3.不剥夺条件:进程已获得的资源，在末使用完之前，不能强行剥夺
>
>4.循环等待条件:若干进程之间形成一种头尾相接的循环等待资源关系。

>个人对死锁的理解：死锁首先发生在一个没有礼让也无法抢夺的环境下，由于一个人占有了一个资源之后，试图去获取另一个资源，而该资源已经被人占用，要想获得这个资源除了等待目前占有者使用完毕之外没有其他方法获取，而目前占有者要完成自己手头工作时，又必须同时获得申请资源者手里占有的资源，同样也无法抢夺，于是两人都进入了无尽的等待状态，也就是死锁。循环等待资源的情况和两个互相等待的情况类似，都是形成了一个头尾相接的等待关系。

### 3.实验感想
>这次实验因为之前操作系统有涉及到过，所以理解方面是比较容易的。这次实验的死锁，主要是因为对于同一个object而言，只能有至多一个线程访问其内部的synchronized同步代码块或同步方法（满足了互斥条件），本次实验就是因为线程t在被唤醒时立即执行了run函数，而run函数内部是一个b的方法，会访问a的last函数，而在它访问a的last函数之前，t线程之后的一个a的方法已经经历完了等待过程（也就是循环过程），并且已经访问了a的方法，此时b的方法再去访问a的last函数（a类的last和method同标记为synchronized），就会被阻塞，进入等待，而此时a的方法又试图去执行b的last函数，由于b.method已经被访问，且未解除访问，故也会进入等待，陷入死锁。由于计算机内部执行速度等原因，每台电脑每次遇到死锁的情况都是不尽相同的，而为了出现死锁情况要将上述程度多次执行的原因也是如此，同时，也增强死锁出现的概率，也就是前一个t线程执行到a的方法时，后一个t线程执行b的方法所可能出现的死锁。理论上讲，要想出现死锁，等待时间不应过长，但如果多次执行，由于第二种死锁出现的情况，就很难说。以上是我对这次实验的理解。


