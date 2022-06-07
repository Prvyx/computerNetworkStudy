##### P13.应用层原理（https://www.bilibili.com/video/BV1JV411t7ow?p=13）

1. ![image-20220515021415197](http://1.15.139.112:5000/static/typoraFigureBed/image-20220515021415197.png)

   （eg：qq聊天就是混合体模式。当双方都在线时，发送信息，使用CS模式和P2P模式；当只有一个人在线时，发送信息，使用CS模式)

   （CS架构可扩展性比较差，可靠性比较差)

   （P2P架构可扩展性好，且用户越多，资源越多，访问越快）

   （eg：qq的P2P：A上线，向服务器报告“我来了”（该注册过程是CS模式），然后服务器维护A的状态；B上线，向服务器报告“我也来了”（该注册过程是CS模式），然后服务器维护B的状态。此时，A想找B聊天，（向服务器发起请求，服务器会查询B的ip地址在哪，然后把B的ip等信息给A）（该目录查询过程是CS模式），A拿到B的ip地址后，直接与B通信）（P2P会话是P2P方式）

2. ![image-20220515025442664](http://1.15.139.112:5000/static/typoraFigureBed/image-20220515025442664.png)

   （TCP Socket实际是一个整数，代表一个四元组{源IP，源端口，目标IP，目标IP的端口号})

   （UDP Socket实际是一个整数，代表一个二元组{源IP，源端口}）

   （Socket不是端口号！！！，而是一个代表{源IP，源端口，目标IP，目标IP的端口号}的一个本地标识，操作系统就可以根据这个本地标识 知道“从我的IP地址、端口号 发给 对方的IP地址、端口号”）

   （操作系统在双方通信过程中维护了Socket这个本地标识，就不用每次在通过SAP（Service Access Point）前get"源IP，源端口，目标IP，目标IP的端口号"，而是直接使用这个在维护状态的本地标识socket）

   ![image-20220515030854497](http://1.15.139.112:5000/static/typoraFigureBed/image-20220515030854497.png)

   （tcp socket是一个本地标识，代表会话关系，代表一个四元组{源IP，源端口，目标IP，目标IP的端口号})

   （应用层通过SAP至tcp传输层，需要传2样东西-数据、tcp socket）

   

   ![image-20220515031626237](http://1.15.139.112:5000/static/typoraFigureBed/image-20220515031626237.png)![image-20220515032729662](http://1.15.139.112:5000/static/typoraFigureBed/image-20220515032729662.png)（udp socket是一个本地标识，不代表会话关系，代表一个二元组，代表{源主机、源端口})

   （应用层通过SAP至udp传输层，需要传3样东西-数据、udp socket、目标主机以及目标主机的目标端口）

   

   举个例子：udp：你不经常向你的一个朋友邮寄东西，你把货物给顺丰，顺丰维护你的信息（源主机、源端口号），但没有维护对方的信息，所以还需要知道发给谁（目标主机、目标主机的目标端口号）；tcp：你经常向你的一个朋友邮寄东西，顺丰维护你的信息以及你的朋友的信息（tcp socket），你直接给顺丰提供货物以及一个tcp socket（实际是一个整数值），顺丰就知道该货物是谁寄的，发给谁的，最终你向顺丰提供了2样东西-货物、tcp socket

3. ![image-20220515033757509](http://1.15.139.112:5000/static/typoraFigureBed/image-20220515033757509.png)![image-20220515034125065](http://1.15.139.112:5000/static/typoraFigureBed/image-20220515034125065.png)

4. ![image-20220515034152851](http://1.15.139.112:5000/static/typoraFigureBed/image-20220515034152851.png)![image-20220515034917614](http://1.15.139.112:5000/static/typoraFigureBed/image-20220515034917614.png)![image-20220515035946991](http://1.15.139.112:5000/static/typoraFigureBed/image-20220515035946991.png)![image-20220515040447091](http://1.15.139.112:5000/static/typoraFigureBed/image-20220515040447091.png)![image-20220515040517540](http://1.15.139.112:5000/static/typoraFigureBed/image-20220515040517540.png)