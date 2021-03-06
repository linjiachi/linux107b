# 第十五週筆記
* 老師家中有事，峯哥代課一週

## 本週主要上課內容
* iptables
    * 如何用 iptables 搭建一套如何企業實際使用的防火牆規則
    * 如何用 iptables 進行防禦攻擊
    * 如何利用 iptables 進行數據包轉發
    * 明白 iptables 的強大及實際使用意義

## linux 指令
* `w`：顯示目前登入使用者相關資訊
```
[user@localhost ~]$ w
 00:33:13 up 3 min,  2 users,  load average: 0.86, 0.53, 0.23
USER 	TTY  	FROM         	LOGIN@   IDLE   JCPU   PCPU WHAT
user 	:0   	:0           	00:30   ?xdm?  27.35s  0.13s /usr/libexec/gnome-ses
user 	pts/0	:0           	00:33	1.00s  0.03s  0.00s w
```
* `iptables -F`：強制清除 iptables 規則

## 什麼是 iptables 
* 常見於 linux 系統下的**應用層**防火牆工具，iptables 用來過濾網路封包，正確的設定 iptables 規則可以有效提升 linux 網路安全，網管人員設定開放哪些 ip 與哪些 port，來阻擋駭客攻擊
* 常用到 iptables 的人員：系統管理人員、網路工程人員、安全人員等等

## 什麼是 netfilter
* 在提到 iptables 之前，我們必須先知道 netfilter 是什麼
* netfilter 是 linux 操作系統核心層內部的一個數據包處理模塊
* 數據包在 netfilter 中的掛載點，我們稱作 **hook point**，分別是 `PREROUTING`、`INPUT`、`OUTPUT`、`FORWARD`、`POSTROUTING` 這五個
* iptables 與 hook point 的關係<br>
    <img src="Week15/hook_point.PNG" width="550px" /> 

## iptables 的 4 張表、5 條鏈
* iptables 規則組成
    * 4 張表 + 5條鏈 (hook point) + 規則
* 4 張表：**filter 表**、**nat 表**、mangle 表、raw 表（後兩種表不常用到）
    * filter 表：訪問控制、規則匹配
    * nat 表：地址轉發
* 5 條鏈：`INPUT`、`OUTPUT`、`FORWARD`、`PREROUTING`、`POSTROUTING`
* 數據包在 4 張表、5 條鏈匹配流程<br>
    <img src="Week15/process.PNG" width="550px" /> 

## 網路 ip
* Class A（1.0.0.0 ～ 126.255.255.255）
* Class B（128.0.0.0 ～ 191.255.255.255）
* Class C（192.0.0.0 ～ 255.255.255.255）

## 延伸學習
1. [慕课网 imooc / 用iptables搭建一套强大的安全防护盾](https://www.imooc.com/learn/389)
2. [防火牆地址轉換 SNAT 及 DNAT](https://blog.csdn.net/chengxuyuanyonghu/article/details/64441374)