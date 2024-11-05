4 subnets , 2 hosts
connect with copper straight thru> pc fast ethernet > switch fast eth
after switch connect to pcs, 2 routers
Switch(cu straight fast eth 03) connect to router(fast eth 00)
After this click on router> physical> turn off router> drag wic 1t to first square> on router> close
Then connect routers with serial dce
Assign ip address to pcs,    (routers ip will be the gateway of the pcs)


Then router0 serial 030 ip=192.168.2.225, subnet=255.255.255.252
Then router1 serial 030 ip=192.168.2.226, subnet=255.255.255.252
router0> config> static> n/w= 192.168.2.128, mask=255.255.255.192, next hop=192.128.2.226
router1> config> static> n/w= 192.168.1.0, mask=255.255.255.0, next hop=192.168.2.225
Then ping any 
