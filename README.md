# ssr4NetgearR7800

- 用到的ipk文件：
- 1. dnsmasq-full_2.89-4_arm_cortex-a15_neon-vfpv4.ipk(用源中opkg install的会报错daemon.crit dnsmasq[1]: recompile with HAVE_IPSET defined to enable ipset directives at line 1 of /tmp/dnsmasq.d/dnsmasq-ssrplus.d/gfw_base.conf)
- 2. bin/packages/arm_cortex-a15_neon-vfpv4/helloworld/*.ipk

```bash
    # UI
    opkg install luci luci-base luci-compat
    # 删除dnsmasq, 此功能会被上面的dnsmasq-full取代
    opkg remove dnsmasq
    # 删除dnsmasq的配置文件
    mv /etc/config/dhcp /etc/config/dhcp.bak
    # 不安装它会无法获取订阅结点
    opkg install luci-lib-ipkg
    # 安装上面所有的ipk
    opkg install *.ipk
```
