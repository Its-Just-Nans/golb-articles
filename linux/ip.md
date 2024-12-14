# Linux ip

## IP

Args

- `-c` : colored output
- `-j` : json output
- `-j -p` : json indented output
- `-d` : more information

| Command `net-tools` | Command `iproute2` | Description             |
| ------------------- | ------------------ | ----------------------- |
| `ifconfig -a`       | `ip addr`          | Show IP address         |
| `arp -a`            | `ip neigh`         | Show ARP table          |
| `route`             | `ip route`         | Show network interfaces |
| `netstat -g`        | `ip maddress`      | multicast               |
