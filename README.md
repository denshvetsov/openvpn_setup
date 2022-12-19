# openvpn_setup
setup openvpn server and clients

use install script from 
https://github.com/angristan/openvpn-install
1. to init server
2. add new clients

allow to see client network 10.0.2.0

1. add to server.conf
sudo nano /etc/openvpn/server.conf

push "route 10.0.1.0 255.255.255.0"
route 10.0.2.0 255.255.255.0
client-to-client
push "route 10.0.2.0 255.255.255.0"

2. add client config
sudo nano /etc/openvpn/ccd/clien-name

iroute 192.168.9.0 255.255.255.0
iroute 10.0.2.0 255.255.255.0
iroute 192.168.88.0 255.255.255.0
iroute 192.168.8.0 255.255.255.0

3. on client side to push vpn local trafic only

