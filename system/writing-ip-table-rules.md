Today I wanted to ssh into my desktop from my laptop. They were both connected to my phone. Laptop was connected via Wi-Fi and the desktop was connected via USB tethering. Since they are not connected in the same way, they were on different networks and it was not possible to ssh into the other computer. I searched about the problem and found [this article](https://www.systutorials.com/port-forwarding-using-iptables/). Since my phone was rooted, I could run any command I want. The final set of commands which allowed me to ssh between each computers were:
```
# from laptop to desktop
iptables -t nat -A POSTROUTING ! -d 192.168.43.0/24 -o rndis0 -j MASQUERADE
iptables -A PREROUTING -t nat -i swlan0 -p tcp --dport 22 -j DNAT --to 192.168.42.17:22
iptables -A FORWARD -p tcp -d 192.168.42.17 --dport 22 -j ACCEPT

# from desktop to laptop
iptables -t nat -A POSTROUTING ! -d 192.168.42.0/24 -o swlan0 -j MASQUERADE
iptables -A PREROUTING -t nat -i rndis0 -p tcp --dport 22 -j DNAT --to 192.168.43.186:22
iptables -A FORWARD -p tcp -d 192.168.43.186 --dport 22 -j ACCEPT

iptables-save
```

Basically, these commands are there to route the traffic from port 22 of device to the port 22 of the other device and accept the incoming connections to port 22. 


At the end of the day, I was able to manage my goal but it didn't worth it. The rules kept resetting when I reset my phone. I thought it would be so much better if I find a Wi-Fi adapter for my desktop so that they will be in the same network. And I bought one :D Phew! Everything was so simple after that.
