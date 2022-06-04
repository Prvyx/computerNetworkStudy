##### P53.各个层次的安全性（https://www.bilibili.com/video/BV1JV411t7ow?p=53）

![image-20220604183801262](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604183801262.png)

###### 安全电子邮件（应用层）

1. 只考虑机密性：

   ![image-20220604184128661](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604184128661.png)

   ![image-20220604184206682](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604184206682.png)（屏蔽了对称密钥分发的问题，也屏蔽了直接用公开密钥的公钥加密明文代价比较大的问题)

2. 考虑可认证性、完整性，不考虑机密性：

   ![image-20220604184325587](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604184325587.png)

3. 考虑机密性、源端可认证性、报文完整性：

   ![image-20220604184536692](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604184536692.png)（eg：PGP)

###### SSL（Secure sockets layer）（传输层）

![image-20220604185452894](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604185452894.png)（理论上 不在传输层，而是在应用层)

###### IPsec（网络层）：AH子协议、ESP子协议等

![image-20220604190003233](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604190003233.png)（AH协议不提供机密性，提供报文完整性和可认证性)（ESP协议提供机密性、报文完整性、源端可认证性)

- AH协议：

  ![image-20220604190418882](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604190418882.png)

- ESP协议：

  ![image-20220604190436717](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604190436717.png)

###### IEEE 802.11 security中的802.11 WEP encryption（链路层）

