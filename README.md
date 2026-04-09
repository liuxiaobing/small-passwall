#### 使用方式
```yaml

默认ssr与passwall的插件与依赖整合包
使用方法：将整合包上传到openwrt设备的tmp目录，输入命令 opkg install *.ipk
默认压缩包里包含ssr passwall passwall2 homeproxy mihomo插件
如果单独安装ssr与依赖，rm -rf {*passwall*,*homeproxy*,*mihomo*}
```

#### 使用
一键命令(防止插件冲突，删除重复)
```yaml
sed -i '1i src-git smallpackages https://github.com/liuxiaobing/small-packages' feeds.conf.default
sed -i '2i src-git smallpasswall https://github.com/liuxiaobing/small-passwall' feeds.conf.default
./scripts/feeds update -a && rm -rf feeds/luci/applications/luci-app-mosdns
rm -rf feeds/packages/net/{alist,adguardhome,mosdns,xray*,v2ray*,sing*,smartdns} feeds/packages/utils/v2dat feeds/packages/lang/golang
git clone https://github.com/kenzok8/golang -b 1.26 feeds/packages/lang/golang
./scripts/feeds install -a
make menuconfig
```
