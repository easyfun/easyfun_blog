Title: HTTP长连接
Date: 2018-02-04 21:00:00
Modified: 2018-02-04 21:00:00
Category: 软件工程
Tags: linux network
Slug:
Author: easyfun

# HTTP长连接

## HTTP短连接与长连接
HTTP协议基于TCP连接，有短连接和长连接两种工作模式。

在短连接下，服务器响应之后立即关闭TCP连接；在长连接模式下，服务器响应之后不会立即关闭TCP连接，等待连接超时时间到达之后才会关闭TCP连接。

在高并发场景下，短连接每次请求服务都需要创建、关闭连接，消耗主机资源，使服务响应时间变长。甚至耗尽服务socket文件句柄数，不能正常对外提供服务。

Linux系统默认最大socket文件数为1024,可以修改系统配置。
socket连接断开之后，有冻结时间，在此期间不可使用，可以修改系统配置，设置socket重用属性。

## HTTP长连接无穷超时

## Spring Cloud通讯层Http工作模式
Spring Cloud通讯层使用Http长连接，还是Http短连接呢？

## Spring Cloud与Dubbo性能比较