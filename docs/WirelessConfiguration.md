# 无线网络配置

为方便调试，423教室配置了一个局域网网络。

|WIFI名称|密码|频段|
|---|---|---|
|elegant_2.4G|82517430|2.4G|
|elegant_5G|82517430|5G|

> [!WARNING]
>
> 这台路由器不开启QoS功能。请不要长时间满带宽下载过大的文件（如百度网盘）。这可能会影响其他人的体验。

> [!WARNING]
>
> 校园网不支持**IPv6**与**SSH服务**，如有需求可以使用手机热点

> [!TIP]
>
> 手机热点(5G)的速率比校园网快很多

# 原理图

通过克隆已认证路由器的mac地址，进而欺骗校园网管理系统

![原理图](https://raw.githubusercontent.com/KirisameLily/elegantai-learning-notes/main/resource/%E5%8E%9F%E7%90%86.png)

# 参数

路由器：小米4A千兆版
**内网速率**：

上行速率：185Mbps
下行速率：126Mbps

> 限于路由器性能，无线模块达不到千兆带宽

**外网速率：**

上行速率：100Mbps
下行速率：100Mbps

经实测，在423教室的各个位置网速都是稳定的，实现了全网覆盖。

# 配置静态地址

在浏览器中输入192.168.31.1，输入管理员密码(见微信群)，进入管理界面

![管理界面](https://raw.githubusercontent.com/KirisameLily/elegantai-learning-notes/main/resource/静态ip_1.png)

依次点击"常用设置"，"局域网设置"。找到最下面"DHCP静态IP分配"，点击"添加设备"

![staticip](https://raw.githubusercontent.com/KirisameLily/elegantai-learning-notes/main/resource/staticipconfig.png)

输入您的设备名称，想要的IP地址，设备的mac地址。保存即可。



> [!CAUTION]
>
> 在分配静态地址前，请使用设备的真实mac地址。关闭设备的"随机mac功能"。如果使用随机mac地址，路由器将无法识别您的设备，不仅会浪费一个IP地址，还会导致静态地址失效。

<img src="https://raw.githubusercontent.com/KirisameLily/elegantai-learning-notes/main/resource/vivomac.png" alt="vivo" style="zoom: 25%;" />



<img src="https://raw.githubusercontent.com/KirisameLily/elegantai-learning-notes/main/resource/ipadmac.png" alt="ipad" style="zoom:50%;" />

在公共场合连接WIFI时，推荐打开"随机mac功能"（例如校园网），可以防止设备mac地址泄露



> [!IMPORTANT]
>
> 请不要占用以下IP地址:
>
> 192.168.31.[$0,1,255$]，这三个IP具有特殊用途（局域网，路由器，网关，广播）
>
> 192.168.31.[$2,3,\cdots,9$]，保留几个IP地址，方便管理与调试
