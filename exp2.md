Network topology refers to the arrangement of different elements like nodes, links, and devices in a computer network. 

It defines how these components are connected and interact with each other. 

Understanding various types of network topologies helps in designing efficient and robust networks.

Common types include bus, star, ring, and mesh topologies.

1. **Bus**
    
    Bus Topology is a network type in which every computer and network device is connected to a single cable called bus. It is bi-directional.
    
    It is a multi-point connection and a non-robust topology because if the backbone fails the topology crashes.
    
    ![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d7f0c0b2-fffe-40d0-9b6d-cae3b360ff45/21e0c4f4-8314-480c-9c27-db9d52e59824/image.png)
    
    Bus topology is familiar technology as installation and troubleshooting techniques are well known.
    
    A common example of bus topology is the Ethernet LAN, where all devices are connected to a single coaxial cable or twisted pair cable. This topology is also used in cable television networks.
    
    - Advantages
        - Works well for small networks
        - Relatively inexpensive to implement
        - Easy to add to it
    - Disadvantages
        - Management costs can be high
        - Potential for congestion with network traffic

1. **Ring**
    
    In a Ring Topology, devices are connected in a ring, each with exactly two neighboring devices.
    
    A number of repeaters are used in a ring topology with many nodes. If someone wants to send data to the last node in a ring topology with 100 nodes, the data must pass through 99 nodes to reach the 100th node. To prevent data loss, repeaters are used in the network.
    
    ![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d7f0c0b2-fffe-40d0-9b6d-cae3b360ff45/cf9a8fcc-afdd-48d8-b3fe-4b23a9366c08/image.png)
    
    The data flows in one direction, i.e., it is unidirectional. However, it can be made bidirectional by having two connections between each network node. This is called Dual Ring Topology.
    
    - Advantages
        - Easier to manage; easier to locate a defective node or cable problem
        - Well-suited for transmitting signals over long distances on a LAN
        - Handles high-volume network traffic
        - Enables reliable communication
    - Disadvantages
        - Expensive
        - Requires more cable and network equipment at the start
        - Not used as widely as bus topology
            - Fewer equipment options
            - Fewer options for expansion to high-speed communication
    
2. **Star**
    
    In Star Topology, every node on the network is connected through a single central hub.
    
    ![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d7f0c0b2-fffe-40d0-9b6d-cae3b360ff45/be10d6b8-b5aa-49b9-9c0e-b3df83a8d89d/image.png)
    
    The hub can be passive, meaning it is not an intelligent hub, like broadcasting devices. Alternatively, the hub can be intelligent, known as an active hub. Active hubs contain repeaters.
    
    - Advantages
        - Good option for modern networks
        - Low startup costs
        - Easy to manage
        - Offers opportunities for expansion
        - Most popular topology in use; wide variety of equipment available
    - Disadvantages
        - Hub is a single point of failure
        - Requires more cable than the bus
    
3. **Mesh**
    
    In a mesh topology, each and every device is connected to every other device via a particular channel. These channels are known as links.
    
    ![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d7f0c0b2-fffe-40d0-9b6d-cae3b360ff45/be5d2637-74dc-4cc7-bbcd-95ae7753f27c/image.png)
    
- Advantages
    - Communication is very fast between the nodes.
    - Mesh Topology is robust.
    - The fault is diagnosed easily. Data is reliable because data is transferred among the devices through dedicated channels or links.
    - Provides security and privacy.
- Disadvantages
    - Installation and configuration are difficult.
    - The cost of cables is high as bulk wiring is required, hence suitable for less number of devices.
    - The cost of maintenance is high.

1. **Hybrid Topology**
    
    This topological technology is the combination of all the various types of topologies.
    
    Hybrid Topology is used when the nodes are free to take any form. It means these can be individuals such as Ring or Star topology or can be a combination of various types of topologies.
    
    ![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d7f0c0b2-fffe-40d0-9b6d-cae3b360ff45/df6c9075-adb8-44c1-a818-9f6b0be49aaf/image.png)
    
- Advantages
    - This topology is **very flexible**.
    - The size of the network can be easily expanded by **adding new devices.**
- Disadvantages
    - It is challenging **to design the architecture** of the Hybrid Network.
    - **Hubs** used in this topology are **very expensive.**
    - The infrastructure cost is very high as a hybrid network **requires a lot of cabling and network devices**.
