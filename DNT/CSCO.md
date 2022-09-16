- [ ] Mail to Darrel on perfect job
- [ ] P2P Ethernet on vpp
- [ ] Projects:
	- [ ] P2P Ethernet
	- [ ] Configuration database
	- [ ] IPv4E
	- [ ] Simplified IPv6
	- [ ] Permission less extensions

- [ ] Spjærholmen brygge årsmøte
- [ ] IP4E
- [ ] SNAC comments
- [ ] NATaaS / VCDP
	- [ ] Policy lookup to enter session dp
	- [ ] Rename to flow router
	- [ ] Classifer. Local traffic, tunnel. Host stack. Etc. 
- [ ] Tegne broer
- [ ] Rute web-site


## Classifier
### Outside interface
- Local host traffic to interface address
- Traffic towards IP pool
- Broadcast traffic to DHCP client
- Static mappings to local pool address
- To NAT, to host stack, to flow router?

All traffic to flow router. Local host entries etc are programmed in the flow table?

### Inside interface 
- local host traffic
- Tunnel headend
- Or tunnel headend on different interface 


Session table lookup. 
If fail:
	Per-something session creation logic
	If DHCP enabled
	If NAT enabled and matches pool etc
	Tunnel end-point

Session lookup match on tunnel
Decap and send to session lookup again 
Fail and go to session create slow path. Session creation policy 
	


### Configuration 

#### VCDP Tunnels 
Are they independent of sessions/vcdp?
A tunnel session is attached to a particular interface. An interface has a given tenant id?
Configured tenant id?
Tunnels live outside of the concept of tenants? Uses default 0 for lookup?


#### inner packet service chain 
Service chain to apply to the inner packet?
A default service chain?

Default for all tenants:
Forward: nat-output / nat-slow path 
Reverse: tunnel-encap

### NAT configuration 
Default pool to use
Per tenant pools


Work description. 
Learn tunnels?





