# Computer Science

## Operating Systems

### BIOS

The BIOS (Basic Input/Output System) is the first operating system that runs when the computer starts up. It allows viewing the characteristics of the components and changing their properties.

### GRUB

GRUB (Grand Unified Bootloader) is the boot system that links the Linux kernel with the operating systems located on the hard drive.

## Application Ports

### Difference Between Ports

- **Hardware port**: Refers to the physical interface where a cable must be connected.
- **Software port**: A point of entry for communication using a specific protocol.

The software port is also called an **application port** because it matches a 16-bit coded number (ranging from 1 to 65536) with an application.

### Main Ports

- **Port 21**: FTP protocol – A file transfer protocol.
- **Port 22**: SSH protocol – Used for almost all remote machine connections. It encrypts exchanges to make intercepted information unreadable.
- **Ports 25, 465, 587**: SMTP protocol – A protocol for sending messages.
- **Port 53**: DNS protocol – Matches an IP address with a domain name and vice versa.
- **Port 67 (server), 68 (client)**: DHCP protocol – Automatically assigns an IP address (and associated addressing configurations such as subnet mask and gateway address) to a node on the network that requests it.

## SMTP Protocol

The SMTP (Simple Mail Transfer Protocol) is the protocol to configure when creating and setting up an email management server (sending). Its default port is **25**.

To receive emails on a client (such as Thunderbird or Outlook), the following protocols can be used:

- **IMAP4**: Allows viewing and making changes directly on the mail server from the client. Only message headers are downloaded. Its default port is **143**.
- **POP3**: Downloads a copy of messages to the computer. This allows working without an internet connection, but a connection is needed to sync new messages. It communicates on port **110**.

## DNS

The DNS (Domain Name System) service is essential for accessing the internet. When the IP address of a website is unknown, the DNS converts the domain name into an IP address and vice versa.

### TLD (Top Level Domain)

TLDs are the extensions at the end of a URL that uniquely identify a FQDN (Fully Qualified Domain Name), which is the complete domain name (including the extension).

### Types of DNS Records

- **A** – Matches an IPv4 address with a domain name.
- **AAAA** – Matches an IPv6 address with a domain name.
- **CNAME** – An alias that links a name to another, usually longer or more complex name.
- **MX** – MX (Mail Exchanger) records link a given name with the mail server for sending emails.

## VNC

VNC (Virtual Network Computing) – A complete solution with detailed settings that allows remote access to troubleshoot a machine (not to be confused with VLC media player).
