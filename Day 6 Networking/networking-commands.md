# Linux Networking Commands 🌐

## Introduction

Networking commands in Linux are used to troubleshoot, monitor, and manage network connections. These commands help users check connectivity, view network configuration, and diagnose network-related issues.

---

# 1. ping

The `ping` command checks connectivity between your system and another host.

Example:

```bash
ping google.com
```

Example Output:

```
64 bytes from 142.250.183.206: icmp_seq=1 ttl=117 time=24.5 ms
```

Explanation:

* Checks if a server is reachable
* Measures response time

Stop ping with:

```
Ctrl + C
```

---

# 2. ifconfig

The `ifconfig` command displays network interface information.

Example:

```bash
ifconfig
```

Example Output:

```
eth0: flags=4163<UP,BROADCAST,RUNNING>
inet 192.168.1.10
```

Explanation:

* Shows IP address
* Shows network interfaces
* Displays MAC address

Note: On modern Linux systems, `ip` command is preferred over `ifconfig`.

---

# 3. ip

The `ip` command is used to show and manage network interfaces.

Show IP address:

```bash
ip a
```

Show routing table:

```bash
ip route
```

Example Output:

```
default via 192.168.1.1 dev eth0
```

Explanation:

* Displays IP addresses
* Shows network interfaces
* Shows routing information

---

# 4. netstat

The `netstat` command shows network connections and listening ports.

Example:

```bash
netstat -tuln
```

Explanation:

* `-t` → TCP connections
* `-u` → UDP connections
* `-l` → Listening ports
* `-n` → Show numerical addresses

Example Output:

```
tcp   0   0 0.0.0.0:22   0.0.0.0:*   LISTEN
```

---

# 5. ss

The `ss` command is a modern replacement for `netstat`.

Example:

```bash
ss -tuln
```

Example Output:

```
Netid State  Recv-Q Send-Q Local Address:Port
tcp   LISTEN 0      128    0.0.0.0:22
```

Explanation:

* Displays active sockets
* Faster than `netstat`

---

# 6. traceroute

The `traceroute` command shows the path packets take to reach a destination.

Example:

```bash
traceroute google.com
```

Example Output:

```
1 192.168.1.1
2 10.10.0.1
3 142.250.183.206
```

Explanation:

* Shows intermediate routers
* Helps diagnose network delays

Install traceroute if needed:

```bash
sudo apt install traceroute
```

---

# 7. curl

The `curl` command transfers data from or to a server.

Example:

```bash
curl https://example.com
```

Check HTTP headers:

```bash
curl -I https://google.com
```

Explanation:

* Used for API testing
* Used to download data
* Used in DevOps automation scripts

---

# 8. wget

The `wget` command downloads files from the internet.

Example:

```bash
wget https://example.com/file.zip
```

Example Output:

```
Saving to: 'file.zip'
```

Explanation:

* Downloads files from web servers
* Supports background downloads
* Can resume interrupted downloads

---

# 9. tracepath

The `tracepath` command traces the route packets take to a destination.

Example:

```bash
tracepath google.com
```

Example Output:

```
1: 192.168.1.1
2: 10.10.0.1
3: 142.250.183.206
```

Explanation:

* Similar to `traceroute`
* Shows packet path to destination
* Does not require root privileges

---

# 10. mtr (My Traceroute)

The `mtr` command combines `ping` and `traceroute` for continuous network diagnostics.

Install:

```bash
sudo apt install mtr
```

Example:

```bash
mtr google.com
```

Explanation:

* Shows real-time network statistics
* Helps detect packet loss and latency

---

# 11. telnet

The `telnet` command tests connectivity to a specific port on a remote host.

Example:

```bash
telnet google.com 80
```

Explanation:

* Tests if a port is open
* Useful for debugging network services

---

# 12. hostname

The `hostname` command displays or sets the system hostname.

Show hostname:

```bash
hostname
```

Set hostname:

```bash
sudo hostname new-hostname
```

Explanation:

* Identifies a system on the network

---

# 13. iwconfig

The `iwconfig` command configures wireless network interfaces.

Example:

```bash
iwconfig
```

Example Output:

```
wlan0  IEEE 802.11  ESSID:"MyWifi"
```

Explanation:

* Displays wireless network settings
* Used for WiFi configuration

---

# 14. arp

The `arp` command displays and modifies the ARP table.

Example:

```bash
arp -a
```

Example Output:

```
192.168.1.1 at 00:14:22:01:23:45 [ether] on eth0
```

Explanation:

* Shows mapping between IP addresses and MAC addresses

---

# 15. dig

The `dig` command is used for DNS lookups.

Example:

```bash
dig google.com
```

Example Output:

```
google.com.   300 IN A 142.250.183.206
```

Explanation:

* Queries DNS servers
* Used for domain troubleshooting

---

# 16. whois

The `whois` command retrieves domain registration information.

Example:

```bash
whois google.com
```

Explanation:

* Shows domain owner information
* Displays registration and expiry details

---

# 17. route

The `route` command displays or modifies the IP routing table.

Example:

```bash
route -n
```

Example Output:

```
Destination     Gateway         Genmask
0.0.0.0         192.168.1.1     0.0.0.0
```

Explanation:

* Shows how packets are routed through the network

---

# 18. nmap

The `nmap` command is used for network scanning and security auditing.

Install:

```bash
sudo apt install nmap
```

Example:

```bash
nmap 192.168.1.1
```

Example Output:

```
PORT   STATE SERVICE
22/tcp open  ssh
80/tcp open  http
```

Explanation:

* Scans open ports
* Used in network security testing

---

# 19. watch

The `watch` command runs a command repeatedly at fixed intervals.

Example:

```bash
watch -n 2 netstat -tuln
```

Explanation:

* Runs the command every 2 seconds
* Useful for monitoring network activity

---

# 20. iptables

The `iptables` command manages Linux firewall rules.

Example:

```bash
sudo iptables -L
```

Example Output:

```
Chain INPUT (policy ACCEPT)
target     prot opt source destination
```

Explanation:

* Controls incoming and outgoing traffic
* Used to configure firewall rules

---

# curl vs wget

Both `curl` and `wget` are used to transfer data from the internet.

| Feature             | curl          | wget           |
| ------------------- | ------------- | -------------- |
| Purpose             | Transfer data | Download files |
| Resume downloads    | Limited       | Yes            |
| API testing         | Yes           | No             |
| Recursive downloads | No            | Yes            |

Example using curl:

```bash
curl https://example.com
```

Example using wget:

```bash
wget https://example.com/file.zip
```

Explanation:

* `curl` → used for APIs and data transfer
* `wget` → used for downloading files

---

# Summary

Linux networking commands help in troubleshooting and managing network connectivity.

Common commands include:

* `ping` → check connectivity
* `ifconfig` → view network interfaces
* `ip` → modern network configuration command
* `netstat` → view network connections
* `ss` → faster alternative to netstat
* `traceroute` → track packet route
* `curl` → transfer data from servers
* `wget` → download files

These commands are essential for **Linux administrators, Cloud engineers, and DevOps professionals**.

---

# Author

Anand Singh
B.Tech Graduate | Learning Linux for Cloud and DevOps
