# mk199
Go语言开发分布式任务调度 ，轻松搞定高性能Crontab
Go语言开发分布式任务调度 ，轻松搞定高性能Crontab
[![下载地址](https://img.mukewang.com/szimg/5fce030c094dc6f005400304.jpg "下载地址")](https://51xueit.vip "下载地址")
[下载地址](https://51xueit.vip "下载地址")
### 第1章 课程介绍 

#### 本章中将介绍一下本课程的基本内容，包括：我们要做什么、要求什么基础、将学会哪些工具、收获哪些独家干货，以及课程具体安排。
1-1 课程导学 (17:00)


### 第2章 如何执行shell命令

#### 执行"定时任务"其实就是执行"shell命令"。在本章中，将首先带大家区分"程序"与"命令"，接着了解bash命令解释器的2种工作模式，并图示分析shell执行任务的底层原理与涉及的系统调用。最后，我们使会用Go语言的Command标准库，实现任务的执行，输出捕获，杀死任务等重要功能。 ...
2-1 原理介绍 (11:55)

2-2 执行任务 (11:39)

2-3 捕获任务输出 (08:02)

2-4 强制结束任务 (13:25)


### 第3章 如何解析cron表达式

#### cron表达式是配置定时任务执行周期的核心工具。在本章中，将首先分析cron表达式的构成以及解析逻辑，并利用开源项目cronexpr解析cron表达式并计算任务的下次调度时间。之后，我们将利用其实现任务并发调度逻辑，即同时调度多个不同的cron任务，作为后续实战课的一个重要前置知识。 ...
3-1 cron表达式原理 (12:42)

3-2 开源cron解析库 (12:47)

3-3 调度多个cron (16:43)


### 第4章 如何应用etcd协调服务 

#### etcd等价于java生态中的zookeeper，基于raft协议工作，用于解决各种分布式应用场景的设计难题。本章中，我们将深入分析raft协议原理，逐步讲解etcd的核心API用法，为实战项目作好准备工作。
4-1 etcd功能与原理(上) (14:04)

4-2 etcd功能与原理(下) (15:01)

4-3 搭建与连接etcd (14:46)

4-4 put写入kv (10:25)

4-5 get读取kv (09:27)

4-6 get读取目录下所有Kv (04:38)

4-7 delete删除kv (09:42)

4-8 lease租约实现kv过期 (19:16)

4-9 watch监听目录变化 (19:39)

4-10 op取代get,put,delete方法 (09:43)

4-11 事务txn实现分布式锁(上) (11:37)

4-12 事务txn实现分布式锁(下) (12:20)


### 第5章 应用mongodb实现分布式存储

#### mongodb是一个分布式的海量存储服务，常用于存储大量的日志类数据。本章中，将首先分析mongodb优势、原理、应用场景，让大家对其架构和功能有所了解。然后，我们会搭建mongodb服务端，开发若干示例程序，包括：插入，查找，删除。后续实战课将使用mongodb完成任务执行日志的保存与查看。 ...
5-1 mongodb简介&基础语法概述 (12:16)

5-2 mongodb原理概述 (14:51)

5-3 搭建与连接mongodb (12:23)

5-4 InsertOne写入单行记录 (14:29)

5-5 InsertMany写入多行记录 (12:19)

5-6 Find查询记录 (12:50)

5-7 Delete删除记录 (11:53)


### 第6章 分布式crontab架构分析

#### 本章中，将带领大家对分布式crontab的整体架构进行功能分析，以及功能拆解。我们会结合整体架构图，包括master节点、worker节点、etcd服务、mongodb服务各自的职责和数据流关系进行相关内容讲解。
6-1 架构分析 (16:21)

6-2 master-worker整体架构 (03:58)

6-3 master功能点与实现思路 (06:23)

6-4 worker功能点与实现思路 (10:22)


### 第7章 实现master

#### 万丈高楼平地起，在本章中，将会带领大家创建github项目，并初始化符合golang规范的项目结构，会带领大家安装依赖的etcd、mongodb包，告诉大家如何正确使用go get命令。之后，我们会逐一实现任务管理API，并实现前后端分离的任务管理后台。...
7-1 创建项目与搭建基本框架(上) (14:26)

7-2 创建项目与搭建基本框架(下) (16:18)

7-3 job save接口开发-保存到etcd(上) (10:02)

7-4 job save接口开发-保存到etcd(中) (10:24)

7-5 job save接口开发-保存到etcd(下) (09:40)

7-6 job delete接口开发：从etcd中删除任务 (14:04)

7-7 job-list接口开发：从etcd获取所有任务 (11:17)

7-8 job-kill接口开发：在etcd中标记结束任务 (12:14)

7-9 http支持静态文件路由 (12:43)

7-10 利用bootstrap搭建页面骨架 (10:36)

7-11 ajax获取任务列表并展示 (15:31)

7-12 实现删除按钮 (05:00)

7-13 实现强杀与编辑按钮 (12:24)

7-14 实现新建任务按钮 (03:34)


### 第8章 实现worker 

#### 在本章中，我们首先让worker实时同步etcd中的任务列表。其次，会基于cronexpr与协程实现一个高并发的定时任务调度模块。我们会通过etcd实现分布式乐观锁，解决多个worker节点并发调度同一个任务的问题。最后，把任务执行的输出与错误码作为日志，保存到mongodb中供web管理后台查看。...
8-1 worker功能概述 (01:52)

8-2 启动后从etcd获取任务列表 (11:01)

8-3 监听etcd中任务变化 (16:13)

8-4 实现任务调度协程(上) (18:20)

8-5 实现任务调度协程(下) (14:36)

8-6 实现任务执行模块(上) (11:13)

8-7 实现任务执行模块(下) (15:03)

8-8 利用分布式锁避免任务并发(上) (13:51)

8-9 利用分布式锁避免任务并发(下) (12:33)

8-10 监听etcd中的强杀任务通知 (16:51)

8-11 保存任务日志到mongodb(上) (15:44)

8-12 保存任务日志到mongodb(中) (13:18)

8-13 保存任务日志到mongodb(下) (05:49)

8-14 运行业务代码中的某个cronjob，代码该如何上传到服务器？

8-15 【讨论题】master如何取得worker的信息？

8-16 【讨论题】master分发任务的架构


### 第9章 完善系统

#### 本章中，我们首先为master添加日志查看API，在web后台可以查看mongodb中保存的任务执行日志。此后，会实现服务注册与发现功能。最后，将演示如何配置nginx upstream反向代理实现高可用的master集群，配置systemctl来实现对master/worker守护进程的保活功能。...
9-1 job-log接口开发之master支持mongodb日志查询 (17:26)

9-2 web界面开发：查看任务执行日志 (15:58)

9-3 worker服务注册到etcd (22:10)

9-4 worker-list接口开发之master从etcd查询worker列表 (07:46)

9-5 web界面开发：查看健康worker列表 (05:34)

9-6 分布式部署到linux服务器(上) (03:46)

9-7 分布式部署到linux服务器（中） (10:44)

9-8 分布式部署到linux服务器(下) (07:37)

9-9 常用命令总结

9-10 【讨论题】现有抢夺任务的架构有有哪些问题和痛点


### 第10章 课程总结&课后练习

#### 本章中，将带领大家回顾整个课程，也给大家提出一些简单可行的课后练习题，包括任务超时限制，任务失败告警。分布式任务调度还有很多细节可以打磨，大家一定要多多动脑动手呦！
10-1 【讨论题】重构系统如何实现更灵活的架构

10-2 课程总结&课后练习 (05:46)


[下载地址](https://51xueit.vip "下载地址")
