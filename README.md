## A C++ Network concurrent server

### Introduction

本项目为以C++编写的负载均衡服务器，实现进程池，灵活性高，能处理多个客户端连接，形成并发模型；并且使用了有限状态机，高效数据封装提高性能。

### Envoirment

* OS: Ubuntu 18.04
* Complier: gcc  7.3.0


### Technical points

（1）使用Epoll边沿触发的IO多路复用技术，非阻塞IO，高效处理事件
采用简单的循环遍历，找出负载最小服务器，达到附载均衡目的

（2）使用多进程充分利用多核CPU，并使用进程池避免进程频繁创建销毁的开销，实现简单的并发CGI server

（3）epoll模型实现的是高并发的聊天室， client：从标准输入中读入数据，并将之发送给客户端

     server： 接受客户端发来的数据并打印，在终端输出
     
（4）并且实现半同步/半反应堆线程池 

### Model
![](https://github.com/GeniusIOTboy1998/NetworkConcurrentServer/blob/master/Model/process.png)

