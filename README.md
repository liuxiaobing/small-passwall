#### 使用
一键命令
```yaml
sed -i '1i src-git smallpasswall https://github.com/liuxiaobing/small-passwall;main' feeds.conf.default
git pull
./scripts/feeds update -a
./scripts/feeds install -a
make menuconfig
```
