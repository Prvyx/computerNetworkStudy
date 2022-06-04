##### P36.自治系统内部的路由选择（https://www.bilibili.com/video/BV1JV411t7ow?p=36）

- RIP协议

  - ![image-20220602215842011](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602215842011.png)（基于DV算法(距离矢量算法)）（最多25个目标子网 -> 适用于小网)（使用跳数这个代价来计算路径)
  - ![image-20220602220331162](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602220331162.png)（RIP进程借助传输层服务使用进程来实现网络层的协议)

- OSPF协议

  - ![image-20220602221011385](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602221011385.png)（基于LS算法(链路状态算法))（可以使用跳数、延迟、拥塞程度这多个代价来计算路径)

  - 在大型网络支持层次化OSPF

    - ![image-20220602221835929](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602221835929.png)(层次化OSPF可以限制链路状态分组泛洪的状态和数量)

      ![image-20220602222200598](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220602222200598.png)