# CTF
##  MISC
---
##  Crypto
---
###  only flag get flag
根据题面意思，
>You can get flag if you carry flag.
>能够拿到flag，如果你拿着flag
拿着flag拿到flag，猜测flag这个单词为密码
根据hint，可知为AES加密
找网站，在线解密即得flag
###  七栅的盖乌斯·尤利乌斯
根据题目可知用了2种加密方法
>七栅代指栅栏解密
>盖乌斯·尤利乌斯，百度可得，是凯撒的名字，即为凯撒解密
题面没什么意思，知道flag和凯撒的生平后，才发现是描写凯撒的。。。
七暗示凯撒解密的偏移量为7，栅栏解密的栏数为7
先凯撒解密，后栅栏解密
```sudo apt-get ```
