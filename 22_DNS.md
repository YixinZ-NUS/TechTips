用DNSMasq或者修改Hosts List或者添加nameserver-policy 来修复GT7无法正确推送更新的问题

原因都是国内的这个APP更新索引服务器和国外的不同步造成的问题
sgst.prod.dl.playstation.net

CDN节点资源都是一样的都有源
但就是获取更新的这个服务器国内节点似乎没有和国外的同步
我们这里需要将这个服务器指向国外的服务器节点IP
或者是用国外DNS来解析这个域名以获得国外的节点IP（推荐）

DNSMasq

或者使用国外的DNS来解析这个服务器域名(推荐,只要DNS一直有效的话一直都可以用无需更新)

servers=/sgst.prod.dl.playstation.net/172.104.93.80

我只是随便找了一一个日本的公共DNS如果无法使用或者解析速度慢的话可以自行在这里找一个合适你的
只需要注意可靠性就行
<https://public-dns.info/nameserver/jp.html>

直接指向国外的服务器节点(不推荐，因为每隔一段时间节点失效了需要手动更新)
address=/sgst.prod.dl.playstation.net/60.87.6.114

Hosts

(不推荐，因为每隔一段时间节点失效了需要手动更新)

60.87.6.114 sgst.prod.dl.playstation.net
复制代码

nameserver-policy (推荐,只要DNS一直有效的话一直都可以用无需更新)
      'sgst.prod.dl.playstation.net': '172.104.93.80'
