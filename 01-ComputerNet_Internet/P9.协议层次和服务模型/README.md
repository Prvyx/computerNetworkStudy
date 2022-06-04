##### P9.协议层次和服务模型（https://www.bilibili.com/video/BV1JV411t7ow?p=9）

1. ![image-20220514151928447](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514151928447.png)（每一层使用其下层提供的服务，向其上层提供服务)（服务：提供的一些功能接口)（军长向团长发布命令，团长向连长发布命令，最后发布命令给士兵)（socket api就是传输层向应用层提供的服务)

2. ![image-20220514152158145](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514152158145.png)（原语：eg，socket api中的“socket创建、socket发送，socket关闭”代码 都是原语)

   ![image-20220514152415191](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514152415191.png)（TCP实体向多个上层用户提供服务，TCP实体会根据不同的SAP（传输层的SAP：port）发给不同的上层用户)（服务是层间的接口interface，在SAP上，通过原语的形式向上层提供服务)

3. 服务的类型：面向连接的服务和无连接的服务

   - ![image-20220514171817817](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514171817817.png)

4. 数据单元、服务数据单元（SDU）、协议数据单元（PDU）

   - ![image-20220514172639566](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514172639566.png)（上层的DU经过封装，变为SDU（服务数据单元），加上ICI控制信息，才能通过SAP，到达下层；下层将IDU中的SDU取出，加上Header（根据ICI以及本层的附加信息生成），生成相应的PDU（协议数据单元）（两个主机的同一层通过PDU交互）)

   - ![image-20220514173314954](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514173314954.png)

   - PDU是统称，在不同层有不同的称呼

     - ![image-20220514182503729](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514182503729.png)

       （应用层：应用报文（message））

       （传输层：报文段（segment））

       （网络层：分组。若是无连接，又叫做数据报）

       （链路层：帧）

       （物理层：比较含糊）

5. 分层的好处：![image-20220514173905929](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514173905929.png)

6. Internet协议栈

   ![image-20220514180443766](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514180443766.png)（47：20)

   （物理层所做的事：将电磁波信号/光信号转为数字信号（0101...），并传输一个个bit/word)

   （链路层所做的事：哪个是帧的开始，哪个是帧的结束。在物理层的基础之上，提供在相邻两点以帧为 单位的数据传输）

   （网络层所做的事：在链路层点到点的基础上，提供端到端/主机到主机的数据传输）

   （传输层所做的事：1.在网络层主机到主机的基础上，完成进程到进程的区分；2.网络层不可靠，传输层可以把它变得可靠（eg：TCP））

   （PPP：以太网的协议）（wifi：WLAN的协议）

7. ISO/OSI 参考模型

   - ![image-20220514180705582](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514180705582.png)（这个参考模型中的表示层、会话层 在 Internet协议栈的应用层去做)

8. 封装和解封装

   - ![image-20220514180953974](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514180953974.png)（1:03:00)（每一层的头部是怎么来的：本层的附加信息以及上层ICI的转换)
   - ![image-20220514181908047](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514181908047.png)(网络层：路由选择、转发功能。将网卡1的帧解封后得到的分组，经过路由选择正确地转发给相应ip的网卡2，转为帧，然后网卡2将帧封装为bit后打出去)