##### P26.可靠数据传输的原理（https://www.bilibili.com/video/BV1JV411t7ow?p=26）

###### 可靠数据传输（rdt）原理

- ![image-20220527000420988](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527000420988.png)

###### rdt的问题描述

- ![image-20220527000911864](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527000911864.png)（对于传输层来说，网络层越可靠，本层所作的工作越少，网络层越不可靠，本层所做的工作越多)
- ![image-20220527001405260](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527001405260.png)（FSM：finite state machine)

###### Rdt各种构造（一步步地完善rdt，一个比一个更复杂，最后得到一个完美、可靠的rdt）（Rdt协议是stop-and-wait 协议，即停等协议）（Rdt协议适用于往返延迟比较低、链路容量比较小的情况下，比如局域网）

- Rdt1.0：在可靠信道上的可靠数据传输

  - ![image-20220527002020708](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527002020708.png)（连长（网络层）很能干，团长（传输层）什么都不干，直接向师长（应用层）交付)

- Rdt2.0：具有比特差错的信道

  - ![image-20220527002349010](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527002349010.png)（在Rdt1.0的基础上，发送方多做的工作：留一个缓存：校验和副本，且当出错时，重发；接收方多做的工作：差错校验，并返回给发送方一个信息：ACK(Acknowledgement)/NAK(Not Acknowledgement))
  - ![image-20220527003315962](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527003315962.png)（extract：解封装；deliver：上交，交付)

- Rdt2.1（原因：Rdt2.0不完备）

  - 背景：Rdt2.0的致命缺陷：发送ACK、NAK的报文段也有可能出错

  - 解决方法：引入了新的机制：序号(sequence number)

  - ![image-20220527004123587](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527004123587.png)

    - 发送方FSM：![image-20220527004721734](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527004721734.png)

    - 接收方FSM：

      ![image-20220527004821316](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527004821316.png)

  - Rdt2.1的运行

    ![image-20220527010048777](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527010048777.png)

- Rdt2.2：无NAK的协议

  - ![image-20220527014013713](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527014013713.png)

  - ![image-20220527013229417](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527013229417.png)（发送方给接收方报文段，报文段错误，但接收方不反馈NAK1（不谢谢你的1），而是ACK0（谢谢你的0）（有点像->问：这个人漂亮吗？回答：这人很温柔）)

    ![image-20220527013240076](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527013240076.png)（这一操作将“停等协议=>流水线协议”做了铺垫。)（对当前分组的反向确认(NAK1)可以用前面一个分组的正向确认(ACK0)来代替)

  - Rdt2.2的运行

    - ![image-20220527014204623](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527014204623.png)(No error、packet error)

      ![image-20220527014656528](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527014656528.png)（ack error)

- Rdt3.0：具有比特差错和分组丢失的信道

  - ![image-20220527020751262](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527020751262.png)(比Rdt2.2多了“超时重传“机制)

  - ![image-20220527015655268](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527015655268.png)（Rdt3.0：no loss、packet loss)

    ![image-20220527015731928](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527015731928.png)（ack loss、delayed ack)

  - 当超时定时器设置不合理时，Rdt3.0还是能正常工作的，但因为重复，导致效率低，所以设置合理的超时定时器也是很重要的：

    ![image-20220527020454801](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527020454801.png)

-------（start-1:02:40说的是Rdt协议（Rdt协议适用于往返延迟比较低、链路容量比较小的情况下，比如局域网））-------

------（1:02:40-1:14:50讲了信道容量、效率的概念，来引出流水线可靠数据传输协议）------ 

###### 流水线（可靠数据传输）协议（适用于往返延迟比较大、链路容量比较大，依次发送多个未经确认的分组）

- ![image-20220527150737726](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527150737726.png)

- GBN、SR比较复杂，先做一点铺垫：滑动窗口协议（更通用的一个协议）

  - ![image-20220527151621633](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527151621633.png)

  - 发送方：

    ![image-20220527152142060](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527152142060.png)

    （**发送窗口是发送缓冲区的子集**)

    ![image-20220527152651929](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527152651929.png)（实际上，当收到确认后，分组队列向左滑动，发送缓冲区不动)（为了便于学习，采用相对滑动的形式，即分组队列不动，发送缓冲区向右滑动)

    ![image-20220527153129954](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527153129954.png)

  - 接收方：

    ![image-20220527154046785](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527154046785.png)

    （**接收窗口=接收缓冲区**)

    ![image-20220527154540012](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527154540012.png)

  - 正常情况下的2个窗口互动

    ![image-20220527155241016](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527155241016.png)

  - 异常情况下GBN的2窗口互动

    ![image-20220527155640381](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527155640381.png)

  - 异常情况下SR的2窗口互动

    ![image-20220527155923128](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527155923128.png)

- GBN协议：

  - ![image-20220527153512643](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527153512643.png)

- SR协议：

  - ![image-20220527153843974](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527153843974.png)

    （若此后p2到来，则可以将接收窗口进行滑动)

- GBN协议与SR协议的异同：

  - ![image-20220527160028692](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527160028692.png)

- 流水线协议总结：

  ![image-20220527160436134](http://1.15.139.112:5000/static/typoraFigureBed/image-20220527160436134.png)

- 关于GBN、SR的FSM：（1:56:56-end）