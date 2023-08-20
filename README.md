iptables -t nat -F

iptables -t mangle -F

iptables -F

iptables -X

iptables -P OUTPUT ACCEPT

iptables -P FORWARD ACCEPT

iptables -P INPUT ACCEPT

iptables -t nat -A POSTROUTING -o eth0   -j MASQUERADE

iptables -t nat -A PREROUTING -p tcp --dport 1234  -j DNAT --to-destination 109.236.91.75:1234

service iptables save

service iptables restart
