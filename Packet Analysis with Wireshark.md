# Packet Analysis with Wireshark

## Objective
To monitor network traffic in real-time and analyze captured packets to uncover sensitive information and detect malicious activity.

## Theory & Concepts
- **Packet Capture (pcap)**: The process of intercepting and logging traffic passing through a network interface.
- **Cleartext Protocols**: Protocols like HTTP, FTP, and Telnet that transmit data without encryption, making them vulnerable to sniffing.
- **SYN Flood**: A type of DoS attack where an attacker sends a succession of SYN requests to a target's system in an attempt to consume enough server resources to make the system unresponsive to legitimate traffic.

## Tools Used
- Wireshark
- hping3 (for traffic simulation)

## Commands & Practical Steps
- **Capture FTP Credentials**:
  - Start Wireshark on `eth1` (Host-Only).
  - On Kali: `ftp 192.168.56.101`.
  - Enter username/password.
  - In Wireshark, filter: `ftp`.
  - Right-click packet → Follow → TCP Stream.
- **Simulate SYN Flood**:
  ```bash
  sudo hping3 -S --flood -V -p 80 192.168.56.101
  ```

## Practical Demonstration Summary
Intercepted an FTP login session and successfully extracted the username and password from the cleartext traffic. Observed the massive influx of SYN packets during a simulated hping3 attack.
