---
highlight: a11y-light
theme: github
---
最近项目要用到一个发票开票接口，但是对方居然用的是webService的方式调用，而我们用的是SpringBoot

IDEA在2019的版本后就没有显示的集成WebService了，导致找了很多种方式，都没有很详细的说明白,具体要
怎么处理，刚好弄清楚，写个笔记记录下

我的IDEA版本2020.1, JDK1.8 项目环境:Springboot 

1.新建module,选择Apach Axis

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/716213f978b44b9295b42ad98f18439f~tplv-k3u1fbpfcp-watermark.image)
![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/30d0ee235b3d4207bf347faacad2b1bc~tplv-k3u1fbpfcp-watermark.image)

2.点击下一步，输入项目名称，后点完成

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/80710833b1544edc8c69119f6157f4ee~tplv-k3u1fbpfcp-watermark.image)

3.出现如下的界面，勾选需要生成的代码，这里要注意 一定要勾选所有的，尤其是测试类代码，可以让你直接测试代码是否生成OK

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/0c3fb690e69048189310212beafb77ae~tplv-k3u1fbpfcp-watermark.image)

4.就会生成如下代码，其中测试类要放到测试模块

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/65653777ddc8497386b285e3e8195498~tplv-k3u1fbpfcp-watermark.image)

5.测试，直接找到对应的测试方法 ，Debug 跑一下 确认代码是否生成OK了

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7e9ceab4de6e41eca27d8e2beb26e86c~tplv-k3u1fbpfcp-watermark.image)

6.最后再项目调试的时候，发现缺了一些maven依赖

```
<dependency>
    <groupId>org.apache.axis</groupId>
    <artifactId>axis</artifactId>
    <version>1.4</version>
</dependency>
<dependency>
    <groupId>javax.xml.rpc</groupId>
    <artifactId>javax.xml.rpc-api</artifactId>
    <version>1.1.2</version>
</dependency>
<dependency>
    <groupId>commons-discovery</groupId>
    <artifactId>commons-discovery</artifactId>
    <version>0.4</version>
</dependency>
```
