node    

> 1.timers   
> 2.pending callbacks   
> 3.close callbacks
4.poll
5.check
6.close 阶段   


```
 1.timers 计时器阶段

　　计时和执行到点的定时器回调函数

 2.pending callbacks

　　某些系统操作（如tcp错误类型）的回调函数

 3.idle ，prepare

　　准备工作

 4.poll 轮询阶段（轮询队列）

　　如果轮询队列不为空，依次同步取出轮询队列中第一个回调执行，知道轮询队列为空或者达到系统最大的限制

　　如果轮询队列为空

　　　　如果之前设置过setImmediate函数

　　　　　　直接进入下一个check阶段

　　　　如果之前没有设置过setImmediate函数

　　　　　　在当前poll阶段等待

　　　　　　　　直到轮询队列添加回调函数，就去第一个情况执行

　　　　　　　　如果定时器到点了，也会去下一个阶段

 5.check 查阶段

　　执行setImmediate设置的回调函数

 6.close callbacks 关闭阶段

　　执行close时间回调函数

 

关于 process.nextTick能在任意优先阶段先执行
```
在poll阶段主要执行两件事：执行I/O回调、处理队列中的事件。

当事件循环在poll阶段时：
1、如果poll队列不为空，则执行队列中的回调；
2、 如果队列中为空，且有setImmediate回调要执行，就会立即停止poll阶段，进入check阶段执行setImmediate的回调；
3、 如果队列为空，并且没有setImmediate回调要执行，poll阶段将等待新的callback被加入。
4、如果有timer的话并且poll队列为空，则会检查是否有timer超时，如果有的话就回到timer阶段，执行相应的回调。
###### 参考资料
https://nodejs.org/zh-cn/docs/guides/event-loop-timers-and-nexttick/
