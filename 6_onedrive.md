#1.mklink创建软链接实现onedrive云同步#
#2.webdav实现#
以下疑似失效:
>先用浏览器登录访问 http://onedrive.com
>随便打开一个文件夹
>然后在地址栏里找 cid=xxxxxxxxxx
>你的webdav 地址就是 https://d.docs.live.net/xxxxxxxxxx
>用户名和密码就是你的 微软账号
>我试过用 winscp作为 webdav客户端能访问

>https://www.chirmyram.top/archives/onedrivewebdav
1.1 实现方式
OneDrive 本身不支持目前通行的 WebDAV 协议，但它自己确实有比较特殊的 WebDAV 服务，只是能支持它的软件很少。以我的 office365 E5 OneDrive 登录后根目录的链接为例：

copy
https://chirmyram-my.sharepoint.com/personal/office_chirmyram_top/_layouts/15/onedrive.aspx
则其对应的 WebDAV 链接为：

copy
https://chirmyram-my.sharepoint.com/personal/office_chirmyram_top/Documents/
观察其特点可发现，将末尾的 /_layouts/15/onedrive.aspx 替换为 /Documents/ 就可以了。末尾 /Documents/ 即为 OneDrive 根目录，也可在其后继续添加子目录。