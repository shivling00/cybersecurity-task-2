# Reconnaissance

## Objective
To gather as much information as possible about a target system or network prior to an active attack, using both passive and active techniques.

## Theory & Concepts
- **Passive Reconnaissance**: Gathering information without directly interacting with the target's systems.
  - **Whois**: Queries databases that store the registered users or assignees of an Internet resource.
  - **Nslookup/Dig**: Querying DNS records for IP addresses, mail servers, etc.
  - **Google Dorking**: Using advanced search operators to find sensitive information indexed by search engines.
  - **Shodan**: A search engine for internet-connected devices.
- **Active Reconnaissance**: Directly interacting with the target (e.g., scanning, banner grabbing).
  - **Ping Sweep**: Identifying active hosts in a network.
  - **Banner Grabbing**: Connecting to services to determine their versions.

## Tools Used
- whois
- nslookup
- whatweb
- shodan.io
- Google Search
- Nmap

## Commands & Practical Steps
- **Whois Search**:
  ```bash
  whois example.com
  ```
- **DNS Recon**:
  ```bash
  nslookup -type=mx example.com
  dig axfr @ns1.example.com example.com # (Zone Transfer attempt)
  ```
- **Active Ping Sweep**:
  ```bash
  nmap -sn 192.168.56.0/24
  ```

## Practical Demonstration Summary
Performed passive reconnaissance on a sample domain to identify its registration details and subdomains. Conducted a ping sweep on the local lab network to map out active IP addresses.
