##### P24.多路复用和解复用（https://www.bilibili.com/video/BV1JV411t7ow?p=24）

###### TCP复用解复用

- ![image-20220526022315157](http://1.15.139.112:5000/static/typoraFigureBed/image-20220526022315157.png)

###### UDP复用解复用

- ![image-20220526023504594](http://1.15.139.112:5000/static/typoraFigureBed/image-20220526023504594.png)

###### TCP复用解复用与UDP复用解复用中握手与不握手的区别：（9：40-10：48）

###### 什么叫“复用”呢？：一个TCP或UDP实体上面有许多应用进程借助它来发送

###### 无连接复用解复用

- ![image-20220526031829393](http://1.15.139.112:5000/static/typoraFigureBed/image-20220526031829393.png)（**在并发的情况下，P1如何区分哪个是P3的，哪个是P4的呢？老师没说**)

###### 面向连接的复用解复用

- ![image-20220526024952378](http://1.15.139.112:5000/static/typoraFigureBed/image-20220526024952378.png)（**只要socket四元组中有一个不一样，就定位到不同的socket，从而定位到不同的应用进程**)（这个视频的作者好像说过：一个端口上可以跑多个进程（我对这句话有点迷糊）)

- （如果是一个多线程的应用进程的话，那么可能是发给同一个进程下的不同的线程）

  ![image-20220526034847457](http://1.15.139.112:5000/static/typoraFigureBed/image-20220526034847457.png)

  ![image-20220526041915040](http://1.15.139.112:5000/static/typoraFigureBed/image-20220526041915040.png)（注：219.157.131.102为当时自己的windows主机的ip地址)