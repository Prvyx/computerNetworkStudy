##### P19.CDN（https://www.bilibili.com/video/BV1JV411t7ow?p=19）

- CDN：互联网杀手级应用

1. 视频业务：视频流量占据着互联网大部分的带宽

2. 异构性：![image-20220518201548147](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220518201548147.png)

3. 普通播放：下载完再播放、流化播放：边下载边播放

4. 多媒体流化服务：DASH（Dynamic,Adaptive Streaming over HTTP）

   - ![image-20220518202320367](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220518202320367.png)

     ![image-20220518203144966](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220518203144966.png)

5. 流化播放取决于服务器、客户端以及链路带宽，而且可能客户端请求服务器的视频资源符合28分布，若不采取措施，会造成发送资源的重复。So，可以采用CDN的方法

6. 在ISP（Internet Service Provider）、ICP（Internet Content Provider）的基础上，这里又多出了CDN运营商。ICP要买CDN的服务，来加快自己的服务

   - ![image-20220518204140203](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220518204140203.png)（CDN的口号：让内容靠近用户)
   - ![image-20220518204651707](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220518204651707.png)（CDN运营商的部署策略)

7. CDN使用manifest file（告示文件）的工作流程（28：45-31：34）

8. 流媒体点播：非实时；实时流媒体加速（eg：春晚（32：05-33：56））

9. 怎么让客户端知道内容从哪个CDN节点访问呢？

   - 通过manifest file（告示文件）
   - 通过DNS的域名解析的重定向（eg：客户端A想要访问服务器B，经过DNS的域名解析重定向，把对服务器B的访问转为对CDN缓存节点C的域名的访问）

10. 在CDN中，内容加速是在网络边缘进行服务的，而不是在网络核心

11. CDN需要解决的问题：

    ![image-20220518210422451](C:\Users\呵\AppData\Roaming\Typora\typora-user-images\image-20220518210422451.png)
    
12. “内容访问场景”的简单示例（38：00-43：35）

    - 其它资料：https://www.bilibili.com/video/BV1uL4y1B7aE

13. “内容访问场景”的实际例子（Netflix：43：38-end）

    - 老师讲的 和 老师用的ppt 好像有些出入