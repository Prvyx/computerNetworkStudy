##### P27.面向连接的传输：TCP（https://www.bilibili.com/video/BV1JV411t7ow?p=27）

###### TCP 概述：

- ![image-20220527183652073](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220527183652073.png)

###### TCP报文段结构：

- ![image-20220527184459305](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220527184459305.png)

###### TCP序号(sequence number)和确认号(acknowledgement number)

- ![image-20220527184936703](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220527184936703.png)

###### TCP是流水线协议，是GBN和SR两种协议的混合体

- ![image-20220527190449258](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220527190449258.png)（TCP的超时重传机制：除了原来的超时定时器超时而触发的超时重传，又多了一个机制-当收到三个冗余ACK，就直接重传（这个重传称为快速重传）)

###### TCP重传

- ![image-20220527192007222](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220527192007222.png)（超时重传机制-正常重传、过早重传)
- ![image-20220527192918593](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220527192918593.png)（快速重传机制-发送方收到来自接收方的3个冗余ack确认，不等超时定时器超时，直接就重发)

###### TCP的流量控制（为了不让发送方发送的太快，接收方接受不了）

- 通过“捎带技术”

  ![image-20220528011659167](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220528011659167.png)（通过反馈，一方将自己的空闲缓冲区的尺寸大小捎带告诉另外一方)

###### TCP建立连接：三次握手，而不是两次握手（1:10:36-1:26:55）

- 两次握手：

  ![image-20220528012503485](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220528012503485.png)

- 三次握手：

  ![image-20220528014010701](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220528014010701.png)

  ![image-20220528013849258](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220528013849258.png)

###### TCP关闭连接：（1:26:55-end）

- ![image-20220528020056523](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220528020056523.png)



