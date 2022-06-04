##### P43.LANs（https://www.bilibili.com/video/BV1JV411t7ow?p=43）

###### ARP、IP地址、MAC地址

![image-20220603203332161](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603203332161.png)（ip地址，经过ARP协议，获得MAC地址。链路层网卡根据MAC地址把ip分组封装为帧，发给另一个网卡)

![image-20220603203557239](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603203557239.png)

###### ARP协议

1. ARP协议：在同一个LAN

   - ![image-20220603204522914](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603204522914.png)

2. ARP协议：路由到其它LAN

   - ![image-20220603204958019](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603204958019.png)

     ![image-20220603204927123](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603204927123.png)

###### 以太网：最流行的LAN技术

- 以太网的第一个版本（总线型）：

  ![image-20220603205746657](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603205746657.png)（NIC：网卡)

- 以太网的三个大版本（29:55-42:21）：

  ![image-20220603210927549](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603210927549.png)（集线器版本的问题：高负载的情况下容易出现冲突，利用率不高)

- 以太网是无连接、不可靠的服务（因为以太网下层的物理层是可靠的）

  ![image-20220603211509013](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603211509013.png)

- 以太网标准：链路层、物理层

  ![image-20220603211726701](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603211726701.png)

- 以太网使用CSMA/CD

-------

###### 物理层：（55:52-end?(?代表：后面的内容可能有些回顾，不只是物理层的内容，没仔细看)）

