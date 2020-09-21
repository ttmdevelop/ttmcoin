# ttmcoin
mainnet protocol implementation

官网首页：http://ttm.ltd/

钱包下载页面： https://pool.bl.top/app/

区块浏览器： https://explorer.bl.top/


节点部署参考：

配置文件：
参考 [ttmcoin.conf](#ttmcoin.conf)


rpc端口：默认 18332 ，可以在配置文件指定


rpc接口说明：
参考 [ttm-cli.md](#ttm-cli.md)



签名算法
[ECDSA](#https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm)



1.将地址进行Base58反编码，得到一个version+public+checksum的字节数组 

2.取version+public+checksum的字节数组的后4个字节为checksum值 

3.取version+public+checksum的字节数组的前21个字节进行两次256哈希运算，取结果值的前4个字节，与第二步中的checksum值进行比较，如果一致则地址有效。

TTM地址正则匹配
if (!(preg_match('/^(1|3)[a-zA-Z\d]{24,33}$/', $address) && preg_match('/^[^0OlI]{25,34}$/', $address))) {
    return false; //满足if代表地址不合法
}











