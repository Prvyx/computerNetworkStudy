##### P49.加密原理（https://www.bilibili.com/video/BV1JV411t7ow?p=49）

- 加密语言：对称密钥加密、非对称密钥加密（公开密钥加密）

  ![image-20220604065238607](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604065238607.png)

  1. 对称密钥加密：

     ![image-20220604065505615](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604065505615.png)

     ![image-20220604065622099](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604065622099.png)

     - 对称密钥加密：DES

       ![image-20220604065814071](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604065814071.png)

       - 密文分组成串技术：

         ![image-20220604070344152](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604070344152.png)

     - 对称密钥加密：AES

       ![image-20220604070920983](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604070920983.png)

  2. 非对称密钥加密：

     ![image-20220604071454525](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604071454525.png)

     ![image-20220604071746884](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604071746884.png)

     - RSA：（下面2个图看不懂的话，推荐视频：https://www.bilibili.com/video/BV1XP4y1A7Ui）

       ![image-20220604071822448](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604071822448.png)（使用了数论的一个定理)

       ![image-20220604072237998](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604072237998.png)（加密与解密的算法是一样的)

     - RSA的一个重要特性：

       ![image-20220604073109304](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220604073109304.png)**（“先公钥，再私钥”用于机密性）（“Alice先用私钥(对数据进行Alice签名)，传给Bob，Bob再用公钥(验证Alice签名的正确性)“非常有用，被用于数字签名)**