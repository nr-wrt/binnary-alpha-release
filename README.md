# RM500U-CNAA/AB 升级 OpenWrt固件说明:

## 升级:
1. 用移远官方升级工具加载pac包, 升级;
2. 升级后 USB 默认 devices 模式: AT, DIAG, LOG, NMEA, RNDIS;
3. Windows 系统安装移远驱动后, 可通过 RNDIS 网口访问 Openwrt 后台;
4. Openwrt 后台 LAN-IP: 192.168.96.1, 用户名: root, 密码: 空;

5. WiFi 默认未开启, 执行:  启动WiFi模块, 默认SSID: Openwrt-2g/5g, 不加密;
```bash
wifi config
wifi up
```

6. 自动拨号默认关闭, 执行: 开启自动驻网拨号, 可上电即有网络服务;
```bash
at_send at+qnetdevctl=1,3,1
```

## beta-version-0.1:
1. 基于标准 Openwrt-21.05 稳定版本移植, 基本功能+软件包开发模式;
2. 业务软件和驱动模块开发, 不再依赖yocto的开发平台;
3. 支持 FC64E 无线网卡;
4. 支持标准 Openwrt 升级接口: sysupgrade, webui升级;
5. 支持 USB-OTG 模式切换, 切换后, 需重启生效;
6. 支持 USB-Host 扩展以太网: 千兆/百兆 (RTL8531B);


### 遗留问题:
1. Openwrt 的 WAN 口协议尚不支持 modem, 目前临时采用'空'配处理;
2. LUCI 的 WiFi 配置页面尚未适配完成, WLAN相关配置, 需要uci指令完成;
3. WLAN的 5G 吞吐性能测试 < 700Mbps (办公室环境);

### 下载地址:

链接：https://pan.baidu.com/s/1NJJtWCnB5zRCHhidSt7MWA?pwd=23gr 

### UI截图
#### overview
![image](https://github.com/nr-wrt/binnary-alpha-release/assets/3498094/1d44bf30-bee2-4768-ba2d-186f0139a38c)
![image](https://github.com/nr-wrt/binnary-alpha-release/assets/3498094/f22337ee-3bd0-45ae-a39a-9cf0c96df829)
#### syslog
![image](https://github.com/nr-wrt/binnary-alpha-release/assets/3498094/2e32bf4f-2e85-43da-83c7-47206af4d31a)
#### interface
![image](https://github.com/nr-wrt/binnary-alpha-release/assets/3498094/50e8d7cf-8f1d-4727-bb78-c91c7e530351)
![image](https://github.com/nr-wrt/binnary-alpha-release/assets/3498094/b3896ab7-c2ba-4ec7-b485-2e8dc70c161f)
#### firewall
![image](https://github.com/nr-wrt/binnary-alpha-release/assets/3498094/1d1bce67-408f-4610-b24a-ec1419da68fc)

#### software packages
![image](https://github.com/nr-wrt/binnary-alpha-release/assets/3498094/7fcea295-0923-4c84-a6c6-9cba9b66f00e)

