#### OpenWrt原生源码+Simons的patch编译，使用前请仔细阅读如下说明：
1. 原版主线OpenWrt，内核5.4，Luci 19.07+SNAPSHOT均当日最新，默认开启BBR，默认开启SFE流量分载。
2. Full版包含adguard home、ssr-plus、docker、ttyd、zerotier、transmission、smartdns、samba4、openclash、frpc/frps、trojan server、应用过滤、ddns、多线多拨（单线多拨无法叠加带宽）等功能
3. Slim版仅有ssrp、trojan-server、frpc/frps、ddns、应用过滤、zerotier及transmission、京东签到等常用功能。 
4. 管理地址: 192.168.1.1 默认空密码
5. 驱动原因，暂只支持rtl8192cu芯片(仅2.4G)及mt76x2u芯片USB无线网卡，rtl8821cu/8811cu的驱动未测试通过，MT7601的驱动不支持AP模式。
6. 已测试支持Hilink模式的4G USB上网卡，NCM模式测试中。
7. 支持第3代金属壳OLED显示R2S系统信息。
8. 仅打包原版bootstrap主题，请勿轻易安装其它主题（19.07多数不兼容）。
9. 建议关闭ipv6的dns解析，以免影响网络体验，Network-DHCP and DNS-Advanced Settings-Filter IPv6 Records。
10. 默认关闭ipv6，有需要的自行开启。
11. 注意R2S网口默认MAC address相同，LAN内同时存在多个R2S请自行修改MAC为唯一。
12. Openwrt原生更新升级功能，支持各种备份、恢复及系统重置。
13. 从友善版固件刷写本固件，建议使用dd写卡：
```
dd if=/tmp/upload/openwrt.img of=/dev/mmcblk0 conv=fsync
```
14. 为避免写卡没有覆盖完全，建议首次启动后先运行firstboot清除再重启一次
15. 上游代码及编译yml更新频繁。自用测试固件，风险自负，不提供任何DaaS.
