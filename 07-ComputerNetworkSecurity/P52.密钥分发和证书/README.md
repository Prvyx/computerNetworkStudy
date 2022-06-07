##### P52.密钥分发和证书（https://www.bilibili.com/video/BV1JV411t7ow?p=52）

###### 两个遗留问题的解决方法：

![image-20220604163441469](http://1.15.139.112:5000/static/typoraFigureBed/image-20220604163441469.png)

- KDC：

  ![image-20220604164300467](http://1.15.139.112:5000/static/typoraFigureBed/image-20220604164300467.png)

- CA

  ![image-20220604165030267](http://1.15.139.112:5000/static/typoraFigureBed/image-20220604165030267.png)

  ![image-20220604165426954](http://1.15.139.112:5000/static/typoraFigureBed/image-20220604165426954.png)

  （前提：获得CA的公钥(如何正确获得CA的公钥呢？：带外的，安装操作系统时，操作系统本身就具备了CA的证书))

  ![image-20220604165838338](http://1.15.139.112:5000/static/typoraFigureBed/image-20220604165838338.png)
  
  （经过这些操作，可靠地获得Bob的公钥，Bob就可以为其它人颁布证书)（以此类推，互联网就建立起这样的“信任树”)