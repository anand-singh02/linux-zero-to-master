# Linux Firewall Configuration and Management 🔥

## Introduction

A firewall is used to control incoming and outgoing network traffic based on predefined security rules.
In Linux, firewalls help protect systems from unauthorized access and network attacks.

Common firewall tools in Linux include:

* `iptables`
* `ufw` (Uncomplicated Firewall)
* `firewalld`

---

# Firewalld Configuration and Management 🔥

## Introduction

`firewalld` is a dynamic firewall management tool used in many Linux distributions such as RHEL, CentOS, and Fedora.
It allows administrators to manage firewall rules using zones, services, and ports without restarting the firewall.

---

# Check if firewalld is Installed

This command checks whether the `firewalld` package is installed on the system.

```bash
rpm -qa | grep firewalld
```

Example Output:

```
firewalld-1.3.0-1.el9.noarch
```

---

# Start or Enable firewalld Service

These commands start the firewall service and enable it to run automatically at system boot.

```bash
sudo systemctl start firewalld
sudo systemctl enable firewalld
```

Stop or disable the service:

```bash
sudo systemctl stop firewalld
sudo systemctl disable firewalld
```

---

# Check firewalld Status

This command shows whether the firewall service is active or inactive.

```bash
sudo systemctl status firewalld
```

Example Output:

```
Active: active (running)
```

---

# Restart firewalld

Restarting the firewall applies configuration changes.

```bash
sudo systemctl restart firewalld
```

---

# Check Firewall Rules

This command shows the currently active firewall rules and configuration.

```bash
sudo firewall-cmd --list-all
```

Example Output:

```
public (active)
services: ssh dhcpv6-client
ports:
```

---

# List All Supported Services

Displays all predefined services known to firewalld.

```bash
sudo firewall-cmd --get-services
```

Example Output:

```
ssh http https ftp samba
```

---

# Reload Firewall Configuration

Reloads firewall rules without restarting the firewall service.

```bash
sudo firewall-cmd --reload
```

---

# List Available Firewall Zones

Firewalld uses zones to manage different trust levels for network connections.

```bash
sudo firewall-cmd --get-zones
```

Example Output:

```
block dmz drop external home internal public trusted work
```

---

# Check Active Zones

Displays currently active firewall zones and their associated network interfaces.

```bash
sudo firewall-cmd --get-active-zones
```

Example Output:

```
public
  interfaces: eth0
```

---

# Show Rules for a Specific Zone

Displays firewall rules configured for a specific zone such as `public`.

```bash
sudo firewall-cmd --zone=public --list-all
```

---

# Add or Remove a Service

Allows or removes a service in the firewall temporarily.

Allow HTTP service:

```bash
sudo firewall-cmd --add-service=http
```

Remove HTTP service:

```bash
sudo firewall-cmd --remove-service=http
```

Reload configuration:

```bash
sudo firewall-cmd --reload
```

---

# Add or Remove Service Permanently

Permanent rules remain after system reboot.

Add service permanently:

```bash
sudo firewall-cmd --add-service=http --permanent
```

Remove service permanently:

```bash
sudo firewall-cmd --remove-service=http --permanent
```

Reload firewall:

```bash
sudo firewall-cmd --reload
```

---

# Add or Remove a Port

Allow traffic on a specific port.

Allow port 20201:

```bash
sudo firewall-cmd --add-port=20201/tcp
```

Remove port:

```bash
sudo firewall-cmd --remove-port=20201/tcp
```

Example:

```
Port 20201 open for TCP traffic
```

---

# Block Incoming Traffic from an IP

This command blocks incoming connections from a specific IP address.

```bash
sudo firewall-cmd --add-rich-rule='rule family="ipv4" source address="192.168.0.10" reject'
```

Example:

```
Traffic from 192.168.0.10 will be rejected
```

---

# Block Outgoing Traffic to an IP

Blocks outgoing traffic from your system to a specific IP.

```bash
sudo firewall-cmd --direct --add-rule ipv4 filter OUTPUT 0 -d 192.168.0.50 -j DROP
```

Example:

```
Outgoing traffic to 192.168.0.50 is blocked
```

---

# Block ICMP (Ping) Requests

This command blocks incoming ICMP traffic such as ping requests.

```bash
sudo firewall-cmd --add-icmp-block-inversion
```

Example:

```
Ping requests will be blocked
```

---


# 1. iptables

`iptables` is a powerful command-line tool used to configure firewall rules in Linux.

## List Firewall Rules

```bash
sudo iptables -L
```

Example Output:

```
Chain INPUT (policy ACCEPT)
target     prot opt source      destination
ACCEPT     all  --  anywhere    anywhere
```

Explanation:

* `INPUT` → Controls incoming traffic
* `OUTPUT` → Controls outgoing traffic
* `FORWARD` → Controls forwarded traffic

---

## Block an IP Address

```bash
sudo iptables -A INPUT -s 192.168.1.10 -j DROP
```

Explanation:

* `-A INPUT` → Add rule to INPUT chain
* `-s` → Source IP address
* `DROP` → Block the traffic

---

## Allow SSH Traffic (Port 22)

```bash
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

Explanation:

* `-p tcp` → Protocol TCP
* `--dport 22` → Destination port 22 (SSH)

---

## Allow HTTP Traffic (Port 80)

```bash
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
```

---

## Delete a Rule

```bash
sudo iptables -D INPUT 1
```

Explanation:

* Deletes rule number 1 from the INPUT chain.

---

# 2. UFW (Uncomplicated Firewall)

`ufw` is a user-friendly firewall tool used mainly in Ubuntu.

## Check Firewall Status

```bash
sudo ufw status
```

Example Output:

```
Status: active
```

---

## Enable Firewall

```bash
sudo ufw enable
```

---

## Disable Firewall

```bash
sudo ufw disable
```

---

## Allow a Port

Allow SSH:

```bash
sudo ufw allow 22
```

Allow HTTP:

```bash
sudo ufw allow 80
```

---

## Deny a Port

```bash
sudo ufw deny 23
```

Explanation:

* Blocks Telnet traffic.

---

## Allow Specific IP

```bash
sudo ufw allow from 192.168.1.20
```

---

## Delete a Rule

```bash
sudo ufw delete allow 80
```

---

# 3. firewalld (Used in RHEL/CentOS)

Check firewall status:

```bash
sudo systemctl status firewalld
```

List active rules:

```bash
sudo firewall-cmd --list-all
```

Allow HTTP service:

```bash
sudo firewall-cmd --add-service=http --permanent
```

Reload firewall:

```bash
sudo firewall-cmd --reload
```

---

# Common Firewall Ports

| Port | Service |
| ---- | ------- |
| 22   | SSH     |
| 80   | HTTP    |
| 443  | HTTPS   |
| 21   | FTP     |
| 25   | SMTP    |

---

# Summary

Linux firewalls help secure systems by filtering network traffic.

Common tools:

* `iptables` → Advanced firewall configuration
* `ufw` → Easy firewall management
* `firewalld` → Dynamic firewall used in enterprise Linux systems

These tools allow administrators to control access to services and protect systems from unauthorized connections.
Firewalld provides flexible firewall management using zones, services, and ports.
It allows administrators to control network traffic and secure Linux systems efficiently.

---

# Author

Anand Singh
B.Tech Graduate | Learning Linux for Cloud and DevOps
