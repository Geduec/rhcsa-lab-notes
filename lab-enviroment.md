# RHCSA Lab Environment

## Virtual Machines

### Server
- Hostname: server.example.com
- Software Selection: Server
- RAM: 4096 MB
- vCPU: 2
- Disk: 30 GB

### Client
- Hostname: cliente.example.com
- Software Selection: Workstation
- RAM: 4096 MB
- vCPU: 2
- Disk: 26 GB

## Network

### VirtualBox
- Network Type: Internal Network
- Network Name: labnet

### Static IPs

| Host | IP Address |
|--------|--------|
| server.example.com | 192.168.26.10/24 |
| client.example.com | 192.168.26.11/24 |

## Verification

Connectivity verified using ping between both hosts.

![Connectivity test](../rhcsa-lab-notes/00-lab-setup/img/ping_servera&client.png)

## Lessons Learned

- Internal Network requires all VMs to use the same network name.
- Hosts must be in the same subnet to communicate.
- Static IPs can be configured using `nmcli` the commands are as follows:

```bash
sudo nmcli con mod enp0s3 ipv4.addresses 192.168.26.X/24
sudo nmcli con mod enp0s3 ipv4.method manual
sudo nmcli con up enp0s3
```