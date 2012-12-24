# Why Pthread?
> 1. 主要推动线程的是他比多进程性能更高。
> 2. 在SMP 体系结果中线程有最大的性能。
> 3. 线程间通信不需要memory cory而进程即使通过共享内存（MPI）
    也会在少一1此copy。 而线程的copy主要是Memory-to-CPU,
    而进程是Memory-to-Memory

# 使用线程的情况
> 1. 支持异步事件
> 2. 长I/O等待
> 3. 一些地方大量使用cpu而有些地方不同用
> 4. 支持优先级作业
> 5. 处理大量并发请求，高响应速度.

# 线程的代价
> 1. 锁的开销
> 2. 同意进程内的线程会相互影响。
> 3. 要有使用线程安全的函数。
> 4. 更难以调试.

# 最佳实践
> 1. 让每个thread做相对独立的大块工作，比让它们做小快工作要好.

# 几种常用的线程编程模型
1.Manager/Worker: 一个管理线程，分配作业给其他线程.
    管理线程处理所有的输入和分配工作.
    这种模型至少有良种方式，1.静态的线程池，2动态线程池

2.pipeline: 线性模式。