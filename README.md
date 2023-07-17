# 基于 RM500U-CNAA/AB 升级OpenWrt固件说明:

## 升级:
1. 直接用移远官方升级工具加载pac包, 升级即可;
2. 升级后USB默认 devices 模式: AT, DIAG, LOG, NMEA, RNDIS;
3. Windows系统安装移远驱动后, 可通过 RNDIS 网口访问 Openwrt 后台;
4. Openwrt 后台 LAN 区 IP: 192.168.96.1, 用户名: root, 密码: 空;

5. WiFi 默认未开启, 执行: 
```
wifi config; 
wifi up; 
```
启动WiFi模块, 默认SSID: Openwrt-2g/5g, 不加密;

6. 自动拨号默认关闭, 执行: 
```
at_send at+qnetdevctl=1,3,1
```
开启自动驻网拨号, 即可上电即有网络服务;



## 当前能力:
1. 基于标准 Openwrt-21.05 稳定版本移植, 举报完整的基本功能和软件包开发模式;
2. 普通业务软件和驱动模块开发, 不再依赖yocto的开发平台;
3. 支持 FC64E 无线网卡;
4. 支持标准 Openwrt 升级接口: sysupgrade, webui升级;
5. 支持 USB-OTG 模式切换, 切换后, 需重启生效;
6. 支持 USB-Host 扩展以太网: 千兆/百兆 (RTL8531B);


## 遗留问题:
1. Openwrt 的 WAN 口协议尚不支持 modem, 目前临时采用'空'配处理;
2. LUCI 的 WiFi 配置页面尚未适配完成, WLAN相关配置, 需要uci指令完成;
3. WLAN的 5G 吞吐性能测试 < 700Mbps (办公室环境);
