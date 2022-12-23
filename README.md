# openvpn_setup
setup openvpn server and clients

use install script from 
https://github.com/angristan/openvpn-install
1. to init server
2. add new clients

<br />allow to see client network 10.0.2.0  outside router has ip 10.0.2.1, subnet 255.255.255.0

1. add to server.conf
<br />sudo nano /etc/openvpn/server.conf

<br />push "route 10.0.1.0 255.255.255.0"
<br />route 10.0.2.0 255.255.255.0
<br />client-to-client
<br />push "route 10.0.2.0 255.255.255.0"

2. add client config on server side
<br />sudo nano /etc/openvpn/ccd/clien-name

<br />iroute 192.168.9.0 255.255.255.0
<br />iroute 10.0.2.0 255.255.255.0
<br />iroute 192.168.88.0 255.255.255.0
<br />iroute 192.168.8.0 255.255.255.0

3. on client side config .ovpn to push vpn local trafic only

<br />route-nopull
<br />route 10.0.1.0 255.255.255.0
