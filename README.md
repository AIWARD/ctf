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
