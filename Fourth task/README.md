Day 4 – Troubleshooting Subnet Mismatch and ARP Resolution Failure

📌 Overview

This experiment demonstrates how a subnet mismatch affects communication between two PCs connected through a Cisco 2960 switch.

The experiment uses Cisco Packet Tracer Simulation Mode to observe ARP requests, ICMP packets, and network communication failures.

🎯 Objective

- To understand subnet mismatch errors.
- To observe ARP resolution in Simulation Mode.
- To identify packet drops and connectivity failures.
- To configure correct IP addresses and restore communication.

🖥️ Network Setup

Connect the following devices:

- PC0
- PC1
- Cisco 2960 Switch

Use Copper Straight-Through cables to connect both PCs to the switch.

IP Configuration

Device| IP Address| Subnet Mask
PC0| 192.168.10.10| 255.255.255.0
PC1| 192.168.20.20| 255.255.255.0

Both devices belong to different subnets.

🔍 Step-by-Step Simulation & Diagnosis

Step 1: Switch to Simulation Mode

1. Open Cisco Packet Tracer.
2. Click the Simulation tab.
3. Open the Simulation Panel.

Step 2: Configure Protocol Filters

1. Click Show All/None.
2. Select Edit Filters.
3. Enable only:
   - ARP (Address Resolution Protocol)
   - ICMP (Internet Control Message Protocol)
4. Close the filter window.

Step 3: Initiate Ping from PC0

Open PC0 → Desktop → Command Prompt.

Execute:

ping 192.168.20.20

Expected Result:

Since both PCs belong to different subnets and no router is configured, PC0 cannot communicate directly with PC1.

The ping may display:

Destination host unreachable.

Step 4: Observe ARP and ICMP Packets

When a host tries to reach a device outside its local subnet, it needs to send the packet through a default gateway.

If no gateway is configured or the gateway cannot be reached, communication fails.

In Simulation Mode:

- Observe ARP requests.
- Track ICMP packet movement.
- Use Capture/Forward to inspect packet processing.
- Examine the PDU Information window to understand packet drops.

Step 5: Understand ARP Resolution

ARP is used to identify the MAC address associated with an IPv4 address.

When the destination is considered local, the sender broadcasts an ARP request to discover the destination MAC address.

Important: A subnet mismatch alone does not make an active destination PC ignore an ARP request addressed to its own IP. For a genuine ARP resolution failure, the target must be unreachable at Layer 2 or otherwise unable to respond.

🛠️ How to Fix the Problem

Return to Realtime Mode and configure both PCs in the same subnet.

Correct IP Configuration

Device| IP Address| Subnet Mask
PC0| 192.168.10.10| 255.255.255.0
PC1| 192.168.10.11| 255.255.255.0

Verify Connectivity

Open PC0 → Desktop → Command Prompt.

Execute:

ping 192.168.10.11

Expected Output:

Reply from 192.168.10.11: bytes=32 time<1ms TTL=128

Ping statistics:
Packets: Sent = 4, Received = 4, Lost = 0

<escape>##</escape> 💻 Important Commands

Command| Purpose
"ping 192.168.20.20"| Tests connectivity to PC1.
"ipconfig /all"| Displays IP configuration.
"arp -a"| Displays ARP entries.
"ping 192.168.10.11"| Verifies corrected connectivity.

✅ Conclusion

This experiment demonstrates how incorrect subnet configuration affects communication between network devices.

By using Cisco Packet Tracer Simulation Mode, ARP and ICMP packet behaviour can be observed and analysed. Correcting the IP addressing and subnet mask allows both PCs to communicate successfully.

Technologies Used: Cisco Packet Tracer, IPv4, ARP, ICMP, Subnetting, Simulation Mode.
