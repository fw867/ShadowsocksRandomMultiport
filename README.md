# ShadowsocksRandomMultiport

#ss 服务端（假设你的目前的服务端 ss 端口已经监听在 423 端口）：

#-----------开始--------------
iptables -t nat -A PREROUTING -p tcp -m multiport --dport 81:1023 -j REDIRECT --to-ports 423
iptables -t nat -A PREROUTING -p udp -m multiport --dport 81:1023 -j REDIRECT --to-ports 423

#以下两条命令可选

service iptables save
service iptables restart

#-----------结束--------------

=============================

客户端

koolss钩选 开启随机多端口
服务器端口 填写 81:1023
