# java.util .concurrent

## 线程安全性

### 加锁机制

#### 内置锁

每个Java对象都可以用做一个实现同步的锁，这些锁被称为内置锁(Intrinsic Lock)或监视器锁(Monitor Lock)。

线程在进入同步代码块之前会自动获得锁，并且在退出同步代码块时自动释放锁，而无论是通过正常的控制路径退出，还是通过从代码块中抛出异常退出。

获得内置对象的唯一途径就是进入由这个锁保护的同步代码块或方法。

Java的内置锁为互斥锁，这意味着最多只有一个线程能持有这种锁。当线程A尝试获取一个由线程B持有的锁时，线程A必须等待或者阻塞，知道线程B释放这个锁。

##### 同步代码块

为Java提供的一种内置的锁机制来支持原子性。同步代码块包括两部分：锁的对象的引用，由这个锁保护的代码块。

##### 同步方法代码块

以关键字synchronized来修饰的方法就是一种横跨整个方法体的同步代码块，其中该同步代码块的锁就是方法调用所在的对象，静态的方法以Class对象作为锁。

#### 重入锁