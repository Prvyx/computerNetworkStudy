##### P32.IP(Internet Protocol)（https://www.bilibili.com/video/BV1JV411t7ow?p=32）

###### Internet的网络层：

- ![image-20220601220740709](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220601220740709.png)（路由协议=>路由表；ip协议查路由表来实现数据平面的转发功能；ICMP协议：信令协议，用来测报错、网通不通(ping命令))

###### IP数据报格式

- ![image-20220601221135356](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220601221135356.png)

  - 分片/重组：

    ![image-20220601221915823](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220601221915823.png)（同一个ip分组中的一片丢失，则该分组的其它片全部丢弃)

    - eg：![image-20220601224536712](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220601224536712.png)![image-20220601224509176](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220601224509176.png)![image-20220601224603514](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220601224603514.png)

###### IP编址

- ![image-20220602024717696](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602024717696.png)

- 子网

  - ![image-20220602025332825](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602025332825.png)（点到点：长途网络；局域网：交换机相连)

- ip地址分类（A类、B类、C类等分配）

  - ![image-20220602025735118](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602025735118.png)（以“网络”为单位做路由信息的传播、计算)

    ![image-20220602030757999](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602030757999.png)

    ![image-20220602031352272](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602031352272.png)

- ip地址分类：CIDR（无类域间路由来分配，按需分配；**引出“子网掩码”**）

  - ![image-20220602032327129](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602032327129.png)

    ![image-20220602032735818](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602032735818.png)（分组的目标ip与表中Mask做&运算，若与Destination Subnet Num匹配，则发至Next hop；若都没匹配上，则一定会和最后的默认表项Default匹配上，通过默认的端口把该分组放出去（默认端口：通常是一个网络的出口，即默认网关）)

###### 如何获得一个ip地址

- ![image-20220602034308826](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602034308826.png)

  - DHCP原理

    ![image-20220602034341592](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602034341592.png)（DHCP协议是基于udp之上的应用层协议)

    ![image-20220602034429826](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602034429826.png)

    ![image-20220602034437069](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602034437069.png)（刚开始，主机使用32位全0地址，广播32位全1地址，试图获得dhcp server的回应)

###### ip编址：如何获得一块地址

- ![image-20220602035219942](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602035219942.png)（所以，你想获得一块ip地址，可以向ICAN来请求一块ip地址，也可以向大的机构去请求分一小块地址给你)

###### 划分子网

- ![image-20220602035632047](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602035632047.png)

  使用了路由聚集、路由通告：

  ![image-20220602040612227](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602040612227.png)

  ![image-20220602040656644](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602040656644.png)

  ![image-20220602042107672](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602042107672.png)（路由聚集的目的：减少路由表的表项，减少路由通告的代价，减少存储和计算的代价)

###### 内网如何与Internet通信（使用内网地址转化）

- ![image-20220602042748495](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602042748495.png)

  ![image-20220602042958103](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602042958103.png)

  ![image-20220602043428477](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602043428477.png)（“出去然后回来” 没问题（内网主动访问外网，即图中的流程），但外网的主动访问内网的设备 就会出现问题（比如内网设备80端口驻留一个web服务器，外网设备并不能与内网设备建立连接）。解决方式：NAT穿越，即**内网穿透**)

- NAT的问题

  ![image-20220602044403963](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602044403963.png)

- NAT穿越/内网穿透 的解决方法

  ![image-20220602044622196](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602044622196.png)

  ![image-20220602044634576](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602044634576.png)

  ![image-20220602044918685](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602044918685.png)

###### IPv6

- IPv6目的：

  ![image-20220602045213490](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602045213490.png)（如果分组太大，路由器不会将其分片，而是会丢弃该分组，然后使用ICMP协议告诉源主机：我是ipv6，这个胖分组太大了，被我干掉了，你发的分组小一点)

- IPv6数据报格式：

  ![image-20220602045818975](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602045818975.png)

  ​	next hdr：（1:48:46-1:49:57)

  ![image-20220602050400841](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602050400841.png)

- 与ipv4的其它变化

  ![image-20220602050457161](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602050457161.png)

- ipv4=>ipv6的平滑过渡：（1:53:00-1:57:11）

  ![image-20220602051159410](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602051159410.png)（将ipv6整个数据报作为ipv4的载荷部分)
