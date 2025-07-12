C++,Linux,Socket,Epoll,多线程               
模拟muduo网络库，用C++11的新特性实现非阻塞IO复用的高并发TCP服务器模型核心(TcpServer),包括 Acceptor, EventThreadPool, Channel, Poller, EventLoop, Buffer ，TcpConnetcion， Logger等模块。


•
整体采用non-blocking+IO-multiplexing+loop线程的设计框架，其中线程模型采用one loop per thread的多线程服务端网络编程模型，结合Reactor 模型进行实现。
•
去掉了Muduo库中的Boost依赖，完全使用C++标准：使用智能指针:unique,shared,weak实现对 Poller,Channel的内存资源释放，对TcpConnection建立和Channel的绑定等。
•
缓冲区参照了 netty的设计,其有一个 prepend、read、write 三个标志,划分缓冲区的数据。
项目收获：通过深入了解muduo网络库的核心-TcpServer源码，对经典的五种IO模型及Reactor模型有了更深的认识；掌握基于事件驱动和事件回调的epoll+线程池面向对象编程；熟悉了网络编程及线程池，缓冲区，学习多线程编程。


核心类的讲解
https://blog.csdn.net/2301_80355452/article/details/149205517?spm=1011.2124.3001.6209
