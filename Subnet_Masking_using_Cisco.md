## Setting a Subnetwork

1. **Add Devices**: 
   - Drag and drop the router, switch, and computers from the bottom of the screen.

2. **Select End Devices**:
   - Choose devices such as routers and computers.

3. **Connect Devices**:
   - Select connections from the bottom left of the screen (e.g., Copper straight-through).
   - Connect devices like **PC0 to Switch0** and **Router0** using a straight-through cable. 
   - For a crossover cable, connect **PC0 to Switch0** and **Router0** accordingly.
   
4. **Connect Multiple PCs**:
   - Repeat the process to connect **PC1, PC2, PC3**, and **Switch1** to **Router0**.

5. **Connect Routers**:
   - To connect **Router0** and **Router1**, use a **serial connection**.
   - Click on **Router0**, turn it off (using the arrow), and select the **WIC 1T interface** to place it in the indicated slot.
   - Repeat the same procedure for **Router1**.

## Configuring the Router in Packet Tracer

1. **Open Ethernet Ports**:
   - The Ethernet ports are physically connected but are in a state called **administrative shutdown**.
   - Access the configuration menu by clicking on the **CLI tab** to allow communication between devices.

# Router0 Configuration
```shell
Router0
--- System Configuration Dialog ---
Continue with configuration dialog? [yes/no]: n
Press RETURN to get started!
Router>enable
Router#configure terminal
Enter configuration commands, one per line. End with CNTL/Z.
Router(config)#interface FastEthernet0/0
Router(config-if)#no shutdown
Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet0/0, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/0, changed state to up
ip address 192.168.1.1 255.255.255.0
Router(config-if)#
Router(config-if)#exit
Router(config)#interface FastEthernet0/1
Router(config-if)#no shutdown
Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet0/1, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/1, changed state to up
ip address 192.168.2.1 255.255.255.0
Router(config-if)#ip address 192.168.2.1 255.255.255.128
Router(config-if)#
Router(config-if)#exit
Router(config)#interface Serial0/3/0
Router(config-if)#no shutdown
%LINK-5-CHANGED: Interface Serial0/3/0, changed state to down
Router(config-if)#no ip address
Router(config-if)#ip address 192.168.2.225 255.255.255.128
Router(config-if)#no ip address
Router(config-if)#ip address 192.168.2.225 255.255.255.128
Router(config-if)#ip address 192.168.2.225 255.255.255.252
Router(config-if)#
%LINK-5-CHANGED: Interface Serial0/3/0, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/3/0, changed state to up
Router con0 is now available
Press RETURN to get started.
Router>enable
Router#configure terminal
Enter configuration commands, one per line. End with CNTL/Z.
Router(config)#ip route 192.168.2.128 255.255.255.192 192.168.2.226
Router(config)#ip route 192.168.2.192 255.255.255.224 192.168.2.226
Router(config)#
Router(config)#end
Router#copy running-config startup-config
Destination filename [startup-config]?
Building configuration...
[OK]
Router#
%SYS-5-CONFIG_I: Configured from console by console
Router con0 is now available
Press RETURN to get started.
%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/3/0, changed state to down
%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/3/0, changed state to up
```
![image](https://github.com/user-attachments/assets/879eb506-4500-4c74-883b-f2842f7f5adc)
![image](https://github.com/user-attachments/assets/86713e9b-7309-4287-9d6e-bf614ac016c4)
![image](https://github.com/user-attachments/assets/d7c1aeaa-786f-424d-8606-fa20e236e355)


# Router1 configuration
```shell
--- System Configuration Dialog ---
Continue with configuration dialog? [yes/no]: n
Press RETURN to get started!
Router>enable
Router#configure terminal
Enter configuration commands, one per line. End with CNTL/Z.
Router(config)#interface FastEthernet0/0
Router(config-if)#no shutdown
Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet0/0, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/0, changed state to up
no ip address
Router(config-if)#ip address 192.168.2.129 255.255.255.0
Router(config-if)#no ip address
Router(config-if)#ip address 192.168.2.129 255.255.255.0
Router(config-if)#ip address 192.168.2.129 255.255.255.192
Router(config-if)#
Router(config-if)#exit
Router(config)#interface FastEthernet0/1
Router(config-if)#no shutdown
Router(config-if)#shutdown
Router(config-if)#no shutdown
Router(config-if)#shutdown
Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet0/1, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/1, changed state to up
%LINK-5-CHANGED: Interface FastEthernet0/1, changed state to administratively down
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/1, changed state to
down
%LINK-5-CHANGED: Interface FastEthernet0/1, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/1, changed state to up
%LINK-5-CHANGED: Interface FastEthernet0/1, changed state to administratively down
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/1, changed state to
down no shutdown
Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet0/1, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/1, changed state to up
ip address 192.168.2.193 255.255.255.192
Router(config-if)#ip address 192.168.2.193 255.255.255.224
Router(config-if)#
Router(config-if)#exit
Router(config)#interface Serial0/3/0
Router(config-if)#no shutdown
Router(config-if)#
%LINK-5-CHANGED: Interface Serial0/3/0, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/3/0, changed state to up
ip address 192.168.2.226 255.255.255.192
% 192.168.2.192 overlaps with FastEthernet0/1
Router(config-if)#ip address 192.168.2.226 255.255.255.252
Router(config-if)#
Router(config-if)#exit
Router(config)#interface Serial0/3/0
Router(config-if)#
Router con0 is now available
Press RETURN to get started.
Router>enable
Router#configure terminal
Enter configuration commands, one per line. End with CNTL/Z.
Router(config)#ip route 192.168.1.0 255.255.255.0 192.168.2.225
Router(config)#ip route 192.168.2.0 255.255.255.128 192.168.2.225
Router(config)#
Router(config)#end
Router#copy running-config startup-config
Destination filename [startup-config]?
Building configuration...
[OK]
Router#
%SYS-5-CONFIG_I: Configured from console by console
Router con0 is now available
Press RETURN to get started.
%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/3/0, changed state to down
%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/3/0, changed state to up
```
![image](https://github.com/user-attachments/assets/595af7d4-28cf-4d00-b8f7-bd9f0bed309d)
![image](https://github.com/user-attachments/assets/6f166dd9-cf30-4797-bf6f-23aa305eb8f2)
![image](https://github.com/user-attachments/assets/ac69ca3a-b12c-4141-b5c1-f77a40fa01d9)

# Static Routing
![image](https://github.com/user-attachments/assets/fce92d5e-a0ec-469a-8883-4cda1dc842d7)
![image](https://github.com/user-attachments/assets/d928c2f0-075d-403c-9ad0-f083612a712e)


# PC Configuration
![image](https://github.com/user-attachments/assets/af1ac3e2-d5e0-4d08-b1aa-1101b5de2a38)
![image](https://github.com/user-attachments/assets/112c06ab-7c3d-485c-accd-3604591e76f0)
![image](https://github.com/user-attachments/assets/f0d27767-87f2-4267-b924-8e44d4314510)
![image](https://github.com/user-attachments/assets/56545467-e9e2-4570-9eb3-8df436bd3ba3)
![image](https://github.com/user-attachments/assets/e89fb15b-29ad-48ae-87d3-2e71cad24a05)
![image](https://github.com/user-attachments/assets/6f9a669c-0b79-4321-8ea5-456f7b3a2f86)
![image](https://github.com/user-attachments/assets/310464e0-211a-4cbf-9ba5-78d3d6fdd2e5)
![image](https://github.com/user-attachments/assets/c9c7e32f-1299-4d55-ac0b-d5240cff2ac5)


# Overall Configuration
![image](https://github.com/user-attachments/assets/4bdcf8ba-98a6-4d16-b616-6b06267679c2)
