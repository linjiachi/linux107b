# 第十週筆記
## ipvsadm 常用參數
* `-C`：清除服務器表中的所有紀錄
* `-l`：顯示虛擬服務器表
* `-c`：顯示 LVS 目前的連接
* `-n`：以數字形式輸出 IP 位址和連接埠

## Keepalived Solution 設定檔
* [linuxvirtualserver.org/The Keepalived Solution](http://www.linuxvirtualserver.org/docs/ha/keepalived.html)

## 不同平台下載指令
* CentOS：`yum install`
* Ubuntu：`apt-get install`

## 五台虛擬機網卡設定
* LVS-1 (router-1、vm-1)：NAT、intnet、Host Only
* LVS-2 (router-2、vm-2)：NAT、intnet、Host Only
* Client：Host Only、intnet
* CentOS 7.0-1 (web-1)：intnet
* CentOS 7.0-2 (web-2)：intnet

## 負載均衡器（Keepalived + LVS）
* keepalived：容錯
* LVS：傳輸效能提升
    * 全名：Linux Virtual Server
    * 虛擬的服務器集群系統
    * 屬於第 4 層（傳輸層）負載平衡器

## 作業
* 由於今天上課老師講的比較快，因此有點來不及做筆記

## 延伸學習
1. [Linux运维日志 centos.bz/LVS Keepalived双机高可用负载均衡搭建](https://www.centos.bz/2017/07/lvs-keepalived-ha-loadbalace/)
2. [Linux运维日志 centos.bz/lvs详细介绍及lvs和keepalived的使用](https://www.centos.bz/2017/09/lvs-intro-and-lvs-keepalived/)