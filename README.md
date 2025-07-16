##### macos将cuhksz的vpn配置为本地sock5节点并加入clash实现分流

###### 安装openconnect和ocproxy

注意需要先安装homebrew

```Shell
brew install openconnect ocproxy
```

###### 运行openconnect并设置为sock5节点

```Shell
echo "PASSWORD" | openconnect -u USERNAME --authgroup='CUHK(SZ)' --script-tun --script='ocproxy -L 2222:unix-host:22 -L 3389:win-host:3389 -D 11080' --passwd-on-stdin vpn.cuhk.edu.cn
```

将上面命令中的USERNAME和PASSWORD分别替换成自己的账号密码即可

###### 将profile导入clash

已经写入了一些常用的域名或ip。如需其他可以在profile最下面的rules中自行添加
