##### P54.防火墙（https://www.bilibili.com/video/BV1JV411t7ow?p=54）

###### 防火墙概念：

![image-20220604214347177](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604214347177.png)

###### 防火墙分类

1. 分组过滤器
2. 应用程序网关

###### 防火墙目的：

![image-20220604215028784](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604215028784.png)

- 分组过滤器（工作在网络层，甚至传输层）：

  - 无状态防火墙的分组过滤：

    ![image-20220604215428712](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604215428712.png)

    ![image-20220604215806744](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604215806744.png)（有点像腾讯云服务器的防火墙，开放 相应端口，没设置的默认deny)

  - 有状态防火墙的分组过滤：

    ![image-20220604220025374](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604220025374.png)（比如外网想要访问内网提供的一个web服务器，tcp/udp连接建立后，才允许相应http流量(访问80号端口)进入内网)

  - 原先的路由器位于网络层，不维护状态，但有些防火墙是特殊的路由器，不仅可以了解网络层的源ip、目标ip，甚至也可以了解传输层的源端口、目标端口。网络层的防火墙已经不仅仅是网络设备，而是一个跨层设备

- 应用程序网关（工作在应用层）

  - ![image-20220604221612766](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604221612766.png)(可以深入管理到各种各样的网络应用)

###### 防火墙的局限性：

![image-20220604222255312](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604222255312.png)（局限性：无法对抗IP spoofing)

