##### P5.网络核心（https://www.bilibili.com/video/BV1JV411t7ow?p=5）

1. 电路交换（circuit switch）
   - ![image-20220513150553973](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513150553973.png)（通过信令)
   - ![image-20220513150907421](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513150907421.png)
   - ![image-20220513151149696](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513151149696.png)（将数据交换节点与数据交换节点之间的链路分片 -> 频分FDM：按频带分；时分TDM：按时间分；波分WDM：用光通信)
   - ![image-20220513151724814](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513151724814.png)
   - ![image-20220513160355527](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513160355527.png)
   - 电路交换不适合计算机之间的通信（计算机之间的通信具有突发性）
     - ![image-20220513160832443](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513160832443.png)
2. 分组交换（packet switch） 
   - 不再像电路交换有时分、波分，你要用全用，传输时使用全部带宽
     - ![image-20220513161155344](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513161155344.png)
   - ![image-20220513161420399](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513161420399.png)（全部存储后转发。向下：存储；向右：转发。每个节点将一个分组的bit全部存储后再进行向下一个节点的转发 全部存储后转发的原因：eg 我要从A到B传10G的文件，若分组不是是全存储后转发，则可能会占用A-B所有的链路，导致其它“主机对”不能使用这些链路的资源，出现网络路径不共享的问题；全存储后转发好处：按需使用，在某一时刻，某“主机对”只会使用一条链路，则其它的“主机对”可以使用其它链路，做到互不影响，从而宏观实现了网络路径的共享)
   - ![image-20220513162808905](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513162808905.png)（31：30）(分组交换比线路交换多了存储时间、不确定的排队时间，换取了共享性，按需使用，没数据传的时候不占用网络的资源，有数据传的时候才占用网络的资源)
   - ![image-20220513164054986](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513164054986.png)![image-20220513164034358](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513164034358.png)(发送时间与接收时间只计算一次就行)(所以，分组交换的总时间：15s，而线路交换的总时间：5s，原因：线路交换中，交换节点是接收1bit，直接转发，不需要对数据所有bit存储完成后再转发，等效于A直接->B，总时间=L/R=5s)（38：00)
   - ![image-20220513164853103](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513164853103.png)
   - ![image-20220513165231877](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513165231877.png)(时分用在线路交换的时分多路复用中，在这里，时分分片是固定的；而有一种特殊的时分多路复用，我们称为“统计多路复用”，存在于分组交换，只不过时分的分片是不固定的，在某一时段，至多有一个分组使用，且使用的时段长度是不固定的)
3. 分组交换vs.电路交换/线路交换
   - ![image-20220513201008231](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513201008231.png)
4. 分组交换根据网络层有没有连接，分为：数据报网络（网络层无连接）、虚电路网络（网络层有连接）
   - 数据报网络：源主机发给目标主机的分组携带了目标主机完整地址，交换节点直接根据目标主机完整地址进行存储和转发。没有hi
     - ![image-20220513202025731](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513202025731.png)(1:03:00)(使用无状态的路由器，不维护主机间的通信状态)
   - 虚电路网络：分组并不携带目标主机完整地址，而是提前hi，然后交换节点会维护一个虚电路号，hi之后的数据交互通过虚电路号进行存储和转发。有hi
     - ![image-20220513202239959](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513202239959.png)（1:05:13)(虚电路靠“信令”建立起来)（有状态：主机H1、H4，以及中间的交换节点都有维护H1与H4的通信状态)
5. 网络分类：![image-20220513202756606](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220513202756606.png)（1:08:22)(注：这些是网络层的东西。分组交换网络中，数据报网络是无连接，虚电路网络是有连接，而TCP是面向连接。因为TCP是进程与进程之间，并没有包括中间的一些交换节点，中间的路由器不维护它们的通信状态；而虚电路网络则是需要主机对和中间的交换节点一起维护通信状态)

