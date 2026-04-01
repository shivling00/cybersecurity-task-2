# Firewall Basics

## Objective
To understand how to configure host-based firewalls to control incoming and outgoing network traffic based on predetermined security rules.

## Theory & Concepts
- **iptables**: A command-line utility for configuring the IP packet filter rules of the Linux kernel firewall.
- **Chains**: INPUT (incoming), OUTPUT (outgoing), FORWARD (routing).
- **Actions**: ACCEPT, DROP, REJECT, LOG.
- **Stateful Inspection**: Monitoring the state of active connections to determine which network packets to allow through the firewall.

## Tools Used
- iptables

## Commands & Practical Steps
- **List Current Rules**:
  ```bash
  sudo iptables -L -n -v
  ```
- **Block a specific IP**:
  ```bash
  sudo iptables -A INPUT -s 192.168.56.1 -j DROP
  ```
- **Allow SSH but block everything else**:
  ```bash
  sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
  sudo iptables -P INPUT DROP
  ```
- **Flush all rules**:
  ```bash
  sudo iptables -F
  ```

## Practical Demonstration Summary
Configured a set of iptables rules on the target machine to block all incoming traffic except for SSH connections. Verified the rules by attempting an Nmap scan from the attacker machine, which resulted in "Filtered" status.
