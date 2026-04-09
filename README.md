#### 使用
一键命令(防止插件冲突，删除重复)
```yaml
sed -i '1i src-git smallpackages https://github.com/kenzok8/small-packages' feeds.conf.default
sed -i '2i src-git smallpasswall https://github.com/kenzok8/small-passwall' feeds.conf.default
./scripts/feeds update -a && rm -rf feeds/luci/applications/luci-app-mosdns
rm -rf feeds/packages/net/{alist,adguardhome,mosdns,xray*,v2ray*,sing*,smartdns} feeds/packages/utils/v2dat feeds/packages/lang/golang
git clone https://github.com/kenzok8/golang -b 1.26 feeds/packages/lang/golang
./scripts/feeds install -a
make menuconfig
