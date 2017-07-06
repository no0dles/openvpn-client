# openvpn-client

## Instructions

1. create a new file auth.txt with the follwing content
```
user@example.com
password123
```

2. copy PrivateKey.key and UserCertificate.crt

3. start a new vpn client
```
docker run -it --rm 
  -v $PWD/vpn:/vpn  
  --cap-add=NET_ADMIN 
  --device /dev/net/tun 
  --sysctl net.ipv6.conf.all.disable_ipv6=0 
  --privileged 
  --name vpn-de 
  no0dles/openvpn-client 
  "config/TunnelBear Germany.ovpn"
```

4. start a new container and link the vpn container
```
docker run -it --rm --net=container:vpn-de ubuntu /bin/bash
```
