# Port & Service Scanning

## Objective
To identify open ports, active services, and the versions of software running on a target system to find potential entry points.

## Theory & Concepts
- **TCP Stealth Scan (-sS)**: The default Nmap scan, which completes only half of the 3-way handshake to avoid being logged by simple firewalls.
- **UDP Scan (-sU)**: Scanning for services running on UDP (which is harder to detect as there is no handshake).
- **Service Detection (-sV)**: Probing open ports to determine service and version information.
- **OS Detection (-O)**: Analyzing TCP/IP stack behavior to guess the target operating system.
- **Nmap Scripting Engine (NSE)**: Using scripts for advanced discovery and vulnerability detection.

## Tools Used
- Nmap

## Commands & Practical Steps
- **Comprehensive Scan**:
  ```bash
  nmap -sS -sV -O -p- 192.168.56.101
  ```
- **UDP Scan**:
  ```bash
  nmap -sU -F 192.168.56.101
  ```
- **Save Output to File**:
  ```bash
  nmap -sS -sV 192.168.56.101 -oN scan_report.txt
  ```

## Practical Demonstration Summary
Conducted a full port scan on the Metasploitable2 machine. Identified critical services like FTP (21), SSH (22), and HTTP (80) along with their specific versions. Created a structured report of the findings.
