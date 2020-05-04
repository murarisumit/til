# Link local address in IPV4

These address are used in zero configuration network, which means these IP address are used in machine in network, where there is no one available(DHCP) to give IP to machine. 

To make is more simpler, when machine boots up OS tried to set address to it's network address.
It gets that by two ways

* Manual config
* DHCP.

If both the mechanisms fail, it then auto-configures itself. 
For auto-configuration it used IP from range of `169.254.0.0/16` i.e. `169.254.0.1 to 169.254.255.254`.

## Procedure

1. Set a random IP from above pool(169.254.0.0/16)
2. It then asks all other computer in network(using ARP), if they have the same IP
3. If someone says yes, it goes back to step 1
4. If someone says no, it selects that random IP.

So this way without any manual config or DHCP server, machine is able to get an IP address.

---

Important part: 
* These address are very always within the network, which means that these address are **not** moved across network via router like private ip range(10.0.0.0/8, 172.31.0.0/16, 192.168.0.0/16). 
* Packets with link-local address are always dropped by router(as there is no guarantees that address is unique beyond it’s network).

---

Further reading:

* https://tools.ietf.org/html/rfc3927
