##### P42.多点访问协议（https://www.bilibili.com/video/BV1JV411t7ow?p=42）

###### 多点访问协议：

- ![image-20220603164908244](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603164908244.png)

###### MAC协议（媒体访问控制协议）：

- ![image-20220603165106425](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603165106425.png)

  - 信道划分：

    ![image-20220603165239898](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603165239898.png)

    ![image-20220603165314005](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603165314005.png)

    ![image-20220603165319251](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603165319251.png)

  - 随机访问：

    ![image-20220603165437861](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603165437861.png)

    - ![image-20220603170332809](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603170332809.png)

      ![image-20220603170417832](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603170417832.png)

    - ![image-20220603170534155](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603170534155.png)

    - CSMA：在发送前先监听一下附近有没有帧在发送。两个节点的距离越短，CSMA发生冲突的概率越小

      ![image-20220603171549647](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603171549647.png)（类比于“类在说话前侦听一下有没有人说话”)

    - CSMA/CD：现在以太网采用的方式

      ![image-20220603172024468](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603172024468.png)（类比于“人类在说话之前侦听，以及在说话过程中侦听”)

      ![image-20220603172146482](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603172146482.png)

    - CSMA/CA（无线局域网）

      ![image-20220603172437634](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603172437634.png)（在WLAN中，信号随着距离衰减；而有线网络中，信号在固体介质上，几乎不衰减)（在WLAN中，别人的信号到你这，但因为自己也在发，CD几乎检测不出来(你的信号>>别人的信号)，所以不采用CSMA/CD中的CD)（在WLAN中，无法CD，做CD也没用)

      ![image-20220603174053562](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603174053562.png)

      ![image-20220603174711746](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603174711746.png)（两个随机回退值-SIFS<DIFS：确认帧的等待时间比数据帧的等待时间小，原因：确认优先级高)

      WLAN运行过程：（1:16:05-1:20:40）

      附：WAN、LAN、WLAN的区别：

      ![image-20220603173012054](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603173012054.png)

    - 线缆接入网络：

      ![image-20220603200004195](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603200004195.png)

      ![image-20220603200325770](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603200325770.png)（上行信道去预约，下行信道把预约的结果发布，所有节点都知道，下行的这些cable modem用户采用预约的结果来使用相应的时隙，然后使用这些时隙来传输数据）（下行不存在竞争，上行存在竞争)

  - 轮流MAC协议（是信道划分MAC协议、随机访问MAC协议的结合体）

    - ![image-20220603201015513](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603201015513.png)（低负载，随机访问MAC协议利用率高；高负载，信道划分MAC协议利用率高（1:37:20-1:38:40))（轮流MAC协议在高负载、低负载都很好，但是轮流MAC协议太复杂了，没人用)

    - 实现：

      1. master轮询：

         ![image-20220603201532333](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603201532333.png)（master若挂了，整个都瘫痪了)

      2. 令牌轮转：

         ![image-20220603201752806](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603201752806.png)（高负载、低负载效率也挺高，但高负载效率高不过信道划分，低负载效率高不过随机访问)

###### MAC协议总结：

- ![image-20220603202314554](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220603202314554.png)