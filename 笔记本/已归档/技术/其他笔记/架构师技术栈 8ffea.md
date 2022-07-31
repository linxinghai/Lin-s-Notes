# 架构师技术栈

Property: April 13, 2022 10:34 PM

架构性能指标

高性能

寻找性能瓶颈

性能测试工具

WEB前端

应用服务器

存储性能优化

安全性

XSS跨站脚本攻击

注入攻击

CSRF跨站点请求伪造

DDoS

其他攻击手段

防火墙

加解密

故障排查

命令

BTrace

JConsole

Memory Analyzer(MAT)

VisualVM

数据分析

方案一

方案二

hadoop

高可用

高可用应用

高可用服务

高可用数据

高可用存储

自动化测试

监控

扩展性

核心思想:模块化

降低模块间的耦合性

提高模块的复用性

分层和分割,以消息传递的依赖调用聚合成完整系统

分布式队列

分布式服务

伸缩性

网站架构伸缩

负载均衡器

分布式缓存集群

数据存储服务器集群

高并发

常见指标

如何提升并发

方法论

方案设计

复杂业务

复杂业务:深入理解

软技能

代码重构

什么是重构

为什么重构

何时重构

何时不该重构

两顶帽子

重构与设计

重构与性能

重构与模式

重构与思想

流程

技术能力

java基础

[数据结构](https://www.notion.so/682fc2ed0b484cbbaa43bf83e7e9dac2)/[设计模式](https://www.notion.so/e5c431197e0b4bf197a7e2687744d6a8)

分布式

微服务

框架源码

互联网工程

git

git补丁

两个相同的repo:repo1和repo2,有修改合并

一个是用git diff 生成的UNIX标准补丁.diff文件

.diff文件只是记录文件改变的内容,不带有commit记录信息,多个commit可以合并成一个diff文件.

git diff的使用方法:

创建:

git diff[commit sha1 id] [commit sha1 id] > [diff文件名]

打入:

git apply [文件名]

二是git format-patch生成的Git专用.patch文件

.patch文件带有记录改变的内容,也带有commit记录信息,每个commit对应一个patch文件.

创建:

git format-patch HEAD^ //最后一次提交补丁

git format-patch HEAD^^ //最后两次提交补丁

git format-patch HEAD-1 //最后一次提交补丁

git format-patch HEAD-2 //最后两次提交补丁

打入:

git am [diff文件名]

maven

idea

jekins

sonarQube

Nginx

Nginx是一个 轻量级/高性能的反向代理Web服务器，他实现非常高效的反向代理、负载平衡，他可以处理2-3万并发连接数，官方监测能支持5万并发，现在中国使用nginx网站用户有很多，例如：新浪、网易、 腾讯等。

Nginx性能这么高？

异步非阻塞事件处理机制：运用了epoll模型，提供了一个队列，排队解决

Nginx应用场景？

http服务器。Nginx是一个http服务可以独立提供http服务。可以做网页静态服务器。

虚拟主机。可以实现在一台服务器虚拟出多个网站，例如个人网站使用的虚拟机。

反向代理，负载均衡。当网站的访问量达到一定程度后，单台服务器不能满足用户的请求时，需要用多台服务器集群可以使用nginx做反向代理。并且多台服务器可以平均分担负载，不会应为某台服务器负载高宕机而某台服务器闲置的情况。

nginz 中也可以配置安全管理、比如可以使用Nginx搭建API接口网关,对每个接口服务进行拦截。

Nginx负载均衡的算法怎么实现的?策略有哪些?

1 轮询(默认)

每个请求按时间顺序逐一分配到不同的后端服务器，如果后端某个服务器宕机，能自动剔除故障系统。

upstream backserver {

server 192.168.0.12;

server 192.168.0.13;

}

2 权重 weight

3 ip_hash( IP绑定)

4 fair(第三方插件)

5、url_hash(第三方插件)

Zookeeper