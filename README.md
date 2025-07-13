## Linux Firewall:

A firewall in Linux is a system for controlling incoming and outgoing network traffic using packet filtering rules. It acts as a barrier between a trusted internal network and untrusted external networks (e.g., the internet).


### Core Linux Firewall Technologies:

#### 1. iptables (legacy, still widely used):
- Traditional firewall utility.
- Uses chains of rules to filter packets.
- Good for manual rule writing and scripting.
- Tool: `iptables`, config: `/etc/sysconfig/iptables`


#### 2. nftables (modern replacement for iptables):
- Unified framework replacing iptables, ip6tables, arptables, and ebtables.
- More efficient and maintainable.
- Default in many newer distros (e.g., Debian 10+, Fedora, RHEL 8+, Rocky Linux 9+).
- Tool: `nft`, config: `/etc/nftables.conf`


#### 3. firewalld (service manager for iptables/nftables):
- High-level daemon to dynamically manage firewall rules.
- Uses zones to define trust levels for interfaces.
- Compatible with both iptables and nftables.
- Tool: `firewall-cmd`, service: `firewalld`



### Choosing the Right Firewall:

| Situation           | Recommended Tool     |
| ------------------- | -------------------- |
| Desktop Linux       | firewalld or UFW     |
| Server Admin        | iptables or nftables |
| cPanel/Hosting      | CSF                  |
| Security Automation | CSF + fail2ban       |



### Linux Firewall Tools & Interfaces:

| Tool        | Backend        | Description                               |
| ----------- | -------------- | ----------------------------------------- |
| `iptables`  | iptables       | Manual low-level control                  |
| `nft`       | nftables       | Modern and flexible firewall tool         |
| `firewalld` | iptables/nft   | Dynamic firewall management via zones     |
| `ufw`       | iptables       | Simple firewall for Ubuntu/Debian         |
| `CSF`       | iptables       | Advanced interface with security features |
| `fail2ban`  | works with any | Auto-bans IPs based on log monitoring     |

