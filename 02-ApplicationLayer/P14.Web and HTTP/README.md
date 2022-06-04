##### P14.Web and HTTP（https://www.bilibili.com/video/BV1JV411t7ow?p=14）

1. URL格式：![image-20220515173429209](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220515173429209.png)（若支持匿名访问，user:psw可以不给；因为是web，所以最后的port默认为80)

2. ![image-20220515174306603](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220515174306603.png)

3. ![image-20220515174549537](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220515174549537.png)

4. 非持久http(http1.0)、持久http(http1.1)![image-20220515175124377](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220515175124377.png)（eg：base.html有10个图片，

   http1.0协议：连接请求、连接确认，发送文件，收到文件，连接关闭，然后客户端使用html解析base.html，发现有10个图片，有几张图片还是之前服务器的，还需重复如上步骤。

   http1.1协议：连接请求、连接确认，发送文件，收到文件，连接不关闭，连接关闭，然后客户端使用html解析base.html，发现有10个图片，有几张图片还是之前服务器的，刚好，之前的连接没关闭，不用再创建连接)

5. http响应时空图

   ![image-20220515175908500](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220515175908500.png)

6. http1.1

   ![image-20220515180223886](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220515180223886.png)(base.html中10个图片资源还在那个存base.html的服务器上，在http1.1中，非流水线：发送pic1的请求，在收到pic1后，再发pic2，依次类推；流水线：一直发发发，不管前一个是否响应)

7. http请求报文格式

   ![image-20220515182246214](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220515182246214.png)（GET：主要目的是从服务器拉取数据、POST：主要目的是向服务器上载数据、HEAD：只要头，例如html文件的头（搜索引擎）)（一个http请求报文：请求行+请求头+请求体（注：一般get请求 不带请求体，post请求 带请求体）)

   ![image-20220515183251013](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220515183251013.png)

   ![image-20220515183857416](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220515183857416.png)

8. http响应报文

   ![image-20220515184306219](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220515184306219.png)

9. cookie

   - **cookie的由来：Http是无状态的协议，无状态：服务器不维护客户端状态。无状态访问网页没问题，但面对复杂的业务就不行了（eg：电子商务网页），我怎么知道你是谁呀？后来对Http进行了改造，引入了cookie，从而把Http由无状态协议=>有状态协议**

   - **cookie的工作流程：（50：13-）**

     ![image-20220515191156361](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220515191156361.png)![image-20220515191802925](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220515191802925.png)

10. Web缓存（**58：32-end（再去看一遍）**）

    - ![image-20220515201748644](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220515201748644.png)（用户端：访问变快；服务器端：负载更轻；网络负担减轻)

      （注：HTTP状态码 304 (Not Modified)，代理server与源server的交互 ）

      （Web缓存只针对服务器静态资源（eg:base.html、1.jpg等），可以访问proxy server而不用访问origin server，动态资源还需要访问origin server（eg：访问b站的推荐视频列表））