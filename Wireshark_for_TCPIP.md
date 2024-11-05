## Wireshark Overview

- **Wireshark**: A free and open-source packet analyzer used for:
  - Network troubleshooting
  - Analysis
  - Software and communications protocol development
  - Education

- **Features**:
  - Graphical front-end similar to tcpdump.
  - Integrated sorting and filtering options.

- **Promiscuous Mode**:
  - Allows network interfaces to capture all traffic visible on that interface, not just traffic addressed to its configured addresses and broadcast/multicast traffic.
  - Note: Capturing in promiscuous mode may not capture all traffic on a network switch unless using port mirroring or network taps.

## Wireshark Installation Steps

1. **Enter Admin Mode**:
   - Run the following command (necessary for packet capture):
     ```bash
     sudo su
     ```

2. **Install Wireshark on Ubuntu**:
   - Use the following command:
     ```bash
     sudo apt-get install wireshark
     ```

3. **Open Wireshark**:
   - Double-click the Wireshark icon to launch the application.

### Figures
- **Figure 1.1**: Wireshark initial interface showing available network interfaces (sudo mode).
- **Figure 1.2**: Example of a Wireshark capture.
- **Figure 2**: Summary of protocols in a Wireshark packet, including information about packet characteristics.
- **Figure 3**: Ethernet II (Layer 2) header in Wireshark.
- **Figure 4**: IP Header (Layer 3).
- **Figure 5**: TCP headers.

## TCP Three-Way Handshake

- The delta value between frames 1 and 2 can serve as a TCP transport connect baseline value.
  
### Important Information Gathered from the Handshake:
- Window Size
- SACK (Selective Acknowledgment)
- Maximum Segment Size
- Window Scale Option value
