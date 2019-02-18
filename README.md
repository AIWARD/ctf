# CTF
##  Crypto
---
###  only flag get flag
根据题面意思，
>You can get flag if you carry flag.   
>能够拿到flag，如果你拿着flag   
拿着flag拿到flag，猜测flag这个单词为密码,根据hint，可知为AES加密,找网站，在线解密即得flag
###  七栅的盖乌斯·尤利乌斯
根据题目可知用了2种加密方法
>七栅代指栅栏解密   
>盖乌斯·尤利乌斯，百度可得，是凯撒的名字，即为凯撒解密   
题面没什么意思，知道flag和凯撒的生平后，才发现是描写凯撒的。。。
七暗示凯撒解密的偏移量为7，栅栏解密的栏数为7
先凯撒解密，后栅栏解密
###  听说你们高中背的很烦啊
根据题面可以知道是社会主义核心价值观
然后百度社会主义核心价值观解密，可得   
[网上关于社会主义核心价值观解密的网站太多钓鱼的，推荐这个](https://sym233.github.io/core-values-encoder/)
###  base家大哥来找事了
根据题面意思可知为base加密，最大的即为base后的数字，最大的即为base92加密  
[关于ctf工具的网站](http://ctf.ssleye.com/)
###  神奇的base
由题目可知为base解密   
```R1kzRE1RWldHRTNET04yQ0c0WlRNT0pXSVEzVEFOU0RHWTJUT1JBPQ==```   
base64的特征为末尾有==（有时候没有）,对如上密文进行解密后得：   
```GY3DMQZWGE3DON2CG4ZTMOJWIQ3TANSDGY2TORA=```   
base32的特征为末尾有=（有时候没有），对如上密文进行解密后得:   
```666C61677B73696D706C657D```   
根据规律猜测为base16，解密可得flag   
###  神秘礼物
压缩包内有1个图片和一个压缩包，解压发现有密码   
看图片发现其中有盲文，对照表发现为压缩密码。压缩包解压后得flag.txt   
###  奇怪的汉字	
当铺密码，每个字有多少出头就代表是几，然后对照ascii表得flag   
###  zwh_hahaha
>挑战题   
>自己加油   
>涉及知识：各种编解码知识
---
##  Misc   
###  TrafficAnalysis   
>下载压缩包后发现是.pcapng,是流量包文，用wireshark打开   
>打开后发现有一项名字是Flags，打开后发现有一条为   ```*******A****```
>推测为flag，查看其他报发现同一位置有其他字母，最后组合为flag   
###  压缩包爆破
根据题面可知，压缩密码为180开头的13位手机号，可以写脚本爆破，也可以用工具
###  一个诡异的压缩包
用winhex打开，发现是伪加密，更改全局加密位和局部加密位，即可解压得flag
###  听说里面还有东西
下载压缩包，解压后，用binwalk识别发现文件末尾有个txt，直接分离，或者用winhex打开可查看
###  一道简单的社工
打开题面的2个url，发现一个是我们学校的官网，另一个是社会工程学的百度词条。猜测flag与学校官网有关系   
打开hint能知道flag与邮箱有关，用whois扫一次学校官网的域名，发现注册邮箱，试了一下，就是flag
###  Least Significant Bit
Least Significant Bit：最低位有效数据隐写术,[解密用脚本的GitHub地址](https://github.com/RobinDavid/LSB-Steganography)
###  一个超极诡异的文件
>挑战题   
>自己加油   
>涉及知识：python，文件批量处理
---
##  Web
###  HTTP-GET
根据代码意思可知，传参给args值，使其等于IWantFlag   
构造payload：
    ```args=IWantFlag```
使用GET方法，可得flag
###  HTTP-POST
根据代码意思可知，传参给args值，使其等于IWantFlag   
构造payload：
    ```args=IWantFlag```
使用POST方法，可得flag
###  web1
通过hint可知有GLOBAL相关漏洞，与GLOBAL相关的有php全局变量漏洞，利用php全局变量漏洞   
（[利用案例及解析](https://www.cnblogs.com/loveyouyou616/archive/2012/11/26/2789150.html)）
构造payload：
    ```args=GLOBALS```
使用GET方法，可得flag
###  web2
通过hint可知是文件包含漏洞，则构造payload查看
构造payload：
    ```?hello=1);echo `cat flag.php`;//```
使用GET或POST方法，可得flag
###  web3
通过hint可知要用GET方法传入参数，array为数组    
利用了[PHP弱类型判定漏洞](https://blog.csdn.net/baidu_41871794/article/details/83750615)
构造payload：
    ```?name[]=12&&password[]=1```
使用GET方法，可得flag
###  Only 1.1.1.1 Can Access
