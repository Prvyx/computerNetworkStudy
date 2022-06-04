##### P8.分组延时、丢失和吞吐量（https://www.bilibili.com/video/BV1JV411t7ow?p=8）

- 传输时延、传播时延

  - ![image-20220514032208478](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514032208478.png)
  - 车队类比：![image-20220514032234074](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514032234074.png)![image-20220514033643364](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514033643364.png)（信道容量大，WAN(wide area network)（广域网）情况)
  - ![image-20220514033747289](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514033747289.png)
  - ![image-20220514033832877](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514033832877.png)（信道容量小，LAN(local area network)（局域网）情况)

- 节点时延

  - ![image-20220514034252475](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514034252475.png)

- 排队时延，取决于流量强度

  - 流量强度：I=(La)/R （L：1个分组的bit长度，单位为bit/分组数；a：单位时间内通过链路转发的分组数量，单位为分组数/时间长度；R：带宽，单位为bps，即bit/时间长度），其中，分子La：单位时间内需要打出去的bit数，分母R：单位时间内最大可以打出去的bit数。流量强度I范围：0~1
    - ![image-20220514042836121](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514042836121.png)
    - 注：R带宽定义（和我最终想的一样）：![image-20220514042558177](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514042558177.png)
    - 中科大老师原话：我的能力（指的分母R）是1Mbps，你要求我传1Mbps（指的是分子La），然后排队延迟就无限大了？为什么？这是作为一个开放性的问题作为大家思考下

- Traceroute（24：20）：使用了ICMP网络层协议

  - ![image-20220514045455676](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514045455676.png)

- 分组丢失以及重传机制（33：32）![image-20220514045534917](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514045534917.png)

  ![image-20220514045939249](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514045939249.png)（若@这条链路是可靠的，则被上一个节点重传；若@这条链路是不可靠的，@链路不重传，则可能被源端系统A重传；若@链路不可靠，且A在传输层使用UDP发送分组，则A也不会重传，丢了就丢了)（@链路可靠的原因：链路层下层的物理层不可靠，链路层需要亡羊补牢（WLAN链路可靠，是因为物理层不可靠）；@链路层不可靠的原因：链路层下面的物理层比较可靠，链路层不需要做额外的工作，不用保证其可靠性（以太网链路不可靠，是因为物理层可靠）)

- 吞吐量

  - 定义

    - ![image-20220514051644169](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514051644169.png)
    - ![image-20220514051716194](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514051716194.png)

  - 理想状态：![image-20220514051830880](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514051830880.png)

  - 实际：某一链路是被共享的

    ![image-20220514052746859](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220514052746859.png)