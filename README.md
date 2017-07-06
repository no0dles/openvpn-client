# openvpn-client

```
docker run -it --rm 
  -v $PWD/vpn:/vpn  
  --cap-add=NET_ADMIN 
  --device /dev/net/tun 
  --sysctl net.ipv6.conf.all.disable_ipv6=0 
  --privileged 
  --name vpn 
  no0dles/openvpn-client 
  --config "config/TunnelBear Germany.ovpn"
```

```
docker run -it --rm --net=container:vpn ubuntu /bin/bash
```
