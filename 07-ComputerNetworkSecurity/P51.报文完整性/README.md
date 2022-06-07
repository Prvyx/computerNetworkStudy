##### P51.报文完整性（https://www.bilibili.com/video/BV1JV411t7ow?p=51）

###### 完整性：完完本本，不被改变

###### 数字签名

- ![image-20220604160636959](http://1.15.139.112:5000/static/typoraFigureBed/image-20220604160636959.png)

  ![image-20220604161405222](http://1.15.139.112:5000/static/typoraFigureBed/image-20220604161405222.png)

  - 一个效率问题：直接对明文m使用私钥加密，会耗费大量时间。解决方法：使用Hash函数生成报文摘要

    ![image-20220604161553936](http://1.15.139.112:5000/static/typoraFigureBed/image-20220604161553936.png)

    （正向计算报文摘要很容易，反向计算很困难)

    附加（学习网络安全概论时的一道题）：
    
    ![image-20220604162309100](http://1.15.139.112:5000/static/typoraFigureBed/image-20220604162309100.png)
  
- ![image-20220604163045385](http://1.15.139.112:5000/static/typoraFigureBed/image-20220604163045385.png)