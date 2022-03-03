# 尝试解决 DNS 污染
>https://www.cnblogs.com/The-explosion/p/15294374.html

1. https://www.ipaddress.com/ 解析
```
140.82.112.4 github.com
185.199.109.153 assets-cdn.github.com
199.232.69.194 github.global.ssl.fastly.net
```

2. 配置静态域名映射，即修改本地电脑系统 hosts 文件

　　Windows 系统中的文件路径：C:\WINDOWS\system32\drivers\etc

　　Linux 系统中的文件路径：/etc/hosts

　　以windows操作系统为例，在C:\Windows\System32\drivers\etc\hosts文件里加我们查到的域名映射

3. 更新dns缓存

　　修改后会保存退出直接生效，无需刷新 DNS 缓存，因为 hosts 的优先级大于 DNS 域名解析，添加完 hosts 之后，再访问对应的域名，已经就与 DNS 没关系了。如果未生效，重启操作系统或用命令刷新一下DNS缓存，在命令行中输入以下命令刷新域名：

## win11 下可用管理员身份打开notepad

Windows 系统：ipconfig /flushdns
Linux 系统：systemctl restart nscd
Mac 系统：sudo dscacheutil -flushcache或sudo killall -HUP mDNSResponder