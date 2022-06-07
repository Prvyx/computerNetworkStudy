##### P37.ISP之间的路由选择：BGP（https://www.bilibili.com/video/BV1JV411t7ow?p=37）

###### ospf协议(基于LS算法)、rip协议(基于DV算法)都不适合非常多的子网的网络，所以就引出了BGP协议

###### 层次路由

- ![image-20220602223327113](http://1.15.139.112:5000/static/typoraFigureBed/image-20220602223327113.png)

  ![image-20220602223530725](http://1.15.139.112:5000/static/typoraFigureBed/image-20220602223530725.png)

###### BGP（外部网关协议）（基于改进的距离矢量算法，避免环路）

- ![image-20220602224024745](http://1.15.139.112:5000/static/typoraFigureBed/image-20220602224024745.png)

  ![image-20220602224059456](http://1.15.139.112:5000/static/typoraFigureBed/image-20220602224059456.png)

  ![image-20220602224500299](http://1.15.139.112:5000/static/typoraFigureBed/image-20220602224500299.png)

  （eBGP、iBGP连接为tcp连接)

- BGP基础：

  ![image-20220602224817395](http://1.15.139.112:5000/static/typoraFigureBed/image-20220602224817395.png)

- BGP路径通告：

  ![image-20220602225034213](http://1.15.139.112:5000/static/typoraFigureBed/image-20220602225034213.png)

  ![image-20220602225220924](http://1.15.139.112:5000/static/typoraFigureBed/image-20220602225220924.png)

  （不一定选择路径最短的路径，而是根据一定的策略来选择路径)

- BGP报文（很复杂）：

  ![image-20220602225420011](http://1.15.139.112:5000/static/typoraFigureBed/image-20220602225420011.png)

###### 内部网关协议(ospf(基于LS算法)、rip(基于DV算法))更关注性能，外部网关协议(bgp(基于改进的DV算法))更关注策略





