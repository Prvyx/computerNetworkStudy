##### P35.路由选择算法（https://www.bilibili.com/video/BV1JV411t7ow?p=35）

###### 路由：

- 路由信息是面向子网工作的，源子网的路由器到目标子网的路由器
- ![image-20220602154142519](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602154142519.png)（主机-主机的路由问题<=>**子网-子网的路由问题**<=>路由器-路由器的路由问题)

###### 最优化原则

- 汇集树

  ![image-20220602154753734](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602154753734.png)

###### 路由原则

- ![image-20220602155048453](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602155048453.png)

###### 路由算法

- 路由算法分类：

  ![image-20220602155725181](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602155725181.png)（分布式的叠代：A有3个邻居B、C、D，B告诉A到北京2元，C告诉A到北京4元，D告诉A到背景5元，然后A知道自己到B、C、D分别是3、4、5元，A叠代地知道了自己到北京的path分别多少钱，找出最小代价的，放在自己的路由表中)

- 路由选择算法：

  - LS路由（链路状态算法）（属于路由算法分类的**全局**路由算法）（基于dijstra算法）

    ![image-20220602160153373](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602160153373.png)

    ![image-20220602160213377](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602160213377.png)（前4步是为了获得路由算法分类的全局路由信息，通过链路状态分组泛洪，获得所有拼图(召唤神龙)，最终获得上帝视角)

    

    防止泛洪的广播风暴：

    ![image-20220602164423507](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602164423507.png)（对方需要返回确认，否则一直发)

    

    dijstra算法（33:46-57:21）

  - DV算法（距离矢量算法）（属于路由算法分类的**分布式**路由算法）（基于动态规划算法）

    - ![image-20220602170031723](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602170031723.png)

      ![image-20220602170041988](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602170041988.png)

      （分布式的叠代：A有3个邻居B、C、D，B告诉A到北京2元，C告诉A到北京4元，D告诉A到背景5元，然后A知道自己到B、C、D分别是3、4、5元，A叠代地知道了自己到北京的path分别多少钱，找出最小代价的，放在自己的路由表中)

      ![image-20220602170626979](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602170626979.png)

      

      距离矢量算法实际基于动态规划（1:10:15-1:16:27）

    - DV算法迭代的时机：

      ![image-20220602171545326](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602171545326.png)

    - DV算法的问题：

      ![image-20220602171818303](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602171818303.png)

      ![image-20220602171827242](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602171827242.png)（A-B是通的=>A-B是不可达的，坏消息传得慢)

      - 坏消息传得慢解决方法：水平分裂算法(又称为毒性逆转)

        ![image-20220602172358750](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602172358750.png)

        ![image-20220602172440185](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602172440185.png)（1:22:48-1:29:02)

  - LS算法(全局，上帝视角)与DV算法(分布式，不断叠代)的对比（1:16:28-1:17:02）：

    LS算法得到全部路由信息后，可以一次性的算出来；而DV算法需要经过不同的叠代，最后才能收敛到最优值真实的状态

    ![image-20220602173306065](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602173306065.png)