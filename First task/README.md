Cisco-Networking-Labs Cisco Packet Tracer networking labs covering IPv4 addressing, LAN configuration, connectivity testing, and basic network troubleshooting.

Single-Host Static IPv4 Addressing & Local Loopback Verification

Objective

Configure a standalone workstation (PC0) with a static IPv4 address in Cisco Packet Tracer and verify the configuration using Command Prompt utilities.

Network Configuration

Parameter Value Device PC0 IPv4 Address 192.168.10.25 Subnet Mask 255.255.255.0 Default Gateway 192.168.10.1 DNS Server 8.8.8.8 Configuration Steps

Added a generic PC to the Cisco Packet Tracer workspace.

Configured PC0 with a static IPv4 address.

Verified the configuration using: ipconfig /all

Tested the local TCP/IP protocol stack using: ping 127.0.0.1

Verified the assigned IP address using: ping 192.168.10.25

Verification

Both ping tests were successful with:

Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)

Tools Used

Cisco Packet Tracer IPv4 TCP/IP Command Prompt Result

The PC0 static IPv4 configuration was successfully assigned and verified using ipconfig and ping.
