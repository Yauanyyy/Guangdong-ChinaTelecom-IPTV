# 广东电信 IPTV 组播转单播源 (Guangdong Telecom IPTV Multicast-to-Unicast Source)

广东电信 IPTV 频道列表 (M3U 格式)。本列表为**组播转单播 (HTTP Proxy)** 格式，每日自动同步更新。
Guangdong Telecom IPTV channel list (M3U format). This list is in **multicast-to-unicast (HTTP Proxy)** format, synced and updated automatically every day.

## ⚠️ 使用说明 / Usage Instructions

本仓库提供的 `.m3u` 文件包含的是经过代理转换的 HTTP 单播地址。使用前请务必根据自身的网络环境进行以下修改：
The `.m3u` files provided in this repository contain HTTP unicast addresses converted via a proxy. Before using, you must make the following modifications based on your own network environment:

### 1. 替换代理服务 IP 和端口 (Replace Proxy Service IP and Port)

本列表中的播放链接并非原始的 UDP/RTP 组播地址，而是经过组播代理转码后的链接。格式如下：
The playback links in this list are not raw UDP/RTP multicast addresses, but links converted via a multicast proxy. The format is as follows:
> `http://192.168.100.1:4022/rtp/239.77.0.84:5146`

其中 `192.168.100.1:4022` 为默认的占位 IP 与端口。
Here, `192.168.100.1:4022` is the default placeholder IP and port.

**操作要求 (Requirement)**：请将其全局替换为您自己在局域网关或软路由上部署的组播代理服务的实际 IP 和端口
Please globally replace it with the actual IP and port of the multicast proxy service deployed on your LAN gateway or router.

### 2. 补全频道台标 / Complete Channel Logos (可选 / Optional)

文件中的台标（Logo）参数格式如下 (The channel logo parameter format in the file is as follows):
> `tvg-logo="http://192.168.100.1:8080/logo/广东卫视.png"`

本仓库不提供台标图片文件，默认链接为无效的内网地址。
This repository does not provide logo image files; the default links are invalid intranet addresses.

**操作方法 (Action)**：如果需要在播放时显示台标，请自行寻找公开的台标库进行批量替换，或在支持的软件中配合第三方 EPG（电子节目单）接口自动匹配。
If you need to display logos during playback, please find public logo libraries for batch replacement yourself, or use a third-party EPG (Electronic Program Guide) interface in supported software for automatic matching.

---
*免责声明：本项目仅供技术交流与网络测试使用，所有地址均来源于公开网络。*
*Disclaimer: This project is for technical exchange and network testing purposes only. All addresses are sourced from the public network.*
