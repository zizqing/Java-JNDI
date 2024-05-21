## 使用同步代码块或同步方法
使用synchronized关键字，确保只有一个线程可以访问同步块或者方法。这样防止多个线程共享资源

## 使用volatile关键字
volatile关键字可以确保多个线程对共享变量的可见性。当一个变量被声明为volatile时，线程在修改这个变量的值时会立即更新到主内存中。

## 使用Lock接口
提供了更灵活的锁定机制。与synchronized关键字相比，Lock接口提供了更多的功能，如可中断的锁、尝试获取锁、定时锁等。

## 使用原子类
Java提供了一些原子类（如AtomicInteger、AtomicLong等），它们提供了一种无锁的线程安全的操作。这些类通过CAS（Compare And Swap）操作来确保线程安全。

## 使用并发集合类
如ConcurrentHashMap、ConcurrentLinkedQueue等

### HashMap

HashMap是由链表和数组构成的，


由于HashMap是线程不同步的，虽然处理数据的效率高，但是在多线程的情况下存在着安全问题。线程不安全是因为HashMap均为多部操作的集合，或者说是非原子的。
### ConcurrentHashMap
ConcurrentHashMap则被提出。