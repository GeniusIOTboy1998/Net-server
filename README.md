## A C++ Network concurrent server

### Introduction

本项目为以C++编写的负载均衡服务器，实现进程池，灵活性高，能处理多个客户端连接，形成并发模型；并且使用了有限状态机，高效数据封装提高性能。

### Envoirment

* OS: Ubuntu 18.04
* Complier: gcc  7.3.0


### Technical points

使用Epoll边沿触发的IO多路复用技术，非阻塞IO

使用多进程充分利用多核CPU，并使用线程池避免线程频繁创建销毁的开销

通过定义一个变量记录每个进程连接数量，而后采用简单遍历，以最小连接新的请求，以此达到负载均衡的目标

主线程统一管理监听socket何连接socket，灵活性高

实现了简单的日志系统

定义进程池类，实现了代码的复用

### Model
![](https://github.com/GeniusIOTboy1998/NetworkConcurrentServer/blob/master/Model/process.png)


### 代码统计

![](https://github.com/GeniusIOTboy1998/NetworkConcurrentServer/blob/master/Model/tree.png)
