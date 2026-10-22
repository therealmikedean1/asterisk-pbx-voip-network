# asterisk-pbx-voip-network
# Internal VoIP Network using Asterisk PBX

## Overview
This project demonstrates the design and implementation of an internal Voice over IP (VoIP) network. It utilizes an open-source Asterisk PBX server running on Linux to route calls between SIP softphones, complete with Call Detail Record (CDR) logging to a MySQL/MariaDB database.

## Technical Stack
* **OS:** Linux Mint
* **PBX Server:** Asterisk 
* **Protocols:** SIP, RTP, TCP/UDP
* **Database:** MariaDB (for CDR logging)
* **Endpoints:** SIP Softphones (Twinkle, Mizudroid)

## Network Topology
```text
[SIP Softphone 1] (Ext 101) ---+
                               |     +-------------------------+
                               +---> |  Asterisk PBX Server    | ---> [MySQL Database]
                               +---> |  (Linux Mint)           |      (CDR Call Logging)
                               |     +-------------------------+
[SIP Softphone 2] (Ext 102) ---+

## Key Configurations
I configured the endpoints and dialplans directly via the command line. The raw configuration files are included in this repository:

sip.conf: Defines the SIP peers, authentication parameters, and network context.

extensions.conf: Contains the dialplan routing logic to connect extensions.

Call Detail Records (CDR) Implementation
To track network usage and call history, the Asterisk server was integrated with a database backend. Below is a snapshot of the live CDR database capturing successful call signaling and routing between the SIP endpoints:
<img width="1366" height="768" alt="Asterisk-CDR-Database" src="https://github.com/user-attachments/assets/57662fdd-1c96-4b92-a52a-c804ab08a0d2" />
