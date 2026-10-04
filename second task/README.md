Single-Host Static IPv4 Addressing & Local Loopback Verification

Lab Overview

This lab demonstrates the configuration of static IPv4 addressing on a standalone workstation using Cisco Packet Tracer. It also verifies the local TCP/IP protocol stack and network interface configuration using Command Prompt utilities.

Objective

To configure a standalone workstation (PC0) with a static IPv4 address and verify the configuration using "ipconfig" and "ping" commands.

Software Required

- Cisco Packet Tracer
- Windows Command Prompt (simulated within Packet Tracer)

Network Configuration

Parameter| Assigned Value
Device Name| PC0
IPv4 Address| 192.168.10.25
Subnet Mask| 255.255.255.0
CIDR Notation| /24
Default Gateway| 192.168.10.1
DNS Server| 8.8.8.8
Interface| FastEthernet0

Procedure

Step 1: Add Device to Workspace

1. Open Cisco Packet Tracer.
2. Select End Devices from the bottom toolbar.
3. Drag a generic PC onto the workspace.
4. The device is identified as PC0.

Step 2: Configure Static IPv4 Address

1. Click PC0.

2. Navigate to the Desktop tab.

3. Select IP Configuration.

4. Choose the Static option.

5. Enter the following details:
   
   - IPv4 Address: 192.168.10.25
   - Subnet Mask: 255.255.255.0
   - Default Gateway: 192.168.10.1
   - DNS Server: 8.8.8.8

6. Close the IP Configuration window.

Step 3: Verify Configuration Using ipconfig

1. Open PC0.
2. Navigate to Desktop → Command Prompt.
3. Execute the following command:

ipconfig /all

Expected Verification:

- Interface: FastEthernet0
- IPv4 Address: 192.168.10.25
- Subnet Mask: 255.255.255.0

Step 4: Test Local Loopback

Execute:

ping 127.0.0.1

This test checks the local TCP/IP protocol stack.

Step 5: Verify Host IP Address

Execute:

ping 192.168.10.25

This test checks the workstation's assigned IP address.

Expected Output

Successful ping verification should display replies similar to:

Reply from 127.0.0.1: bytes=32 time<1ms TTL=128

Reply from 192.168.10.25: bytes=32 time<1ms TTL=128

Expected packet statistics:

- Sent = 4
- Received = 4
- Lost = 0 (0% loss)

Note: These are expected success criteria. Actual results should be verified in Cisco Packet Tracer.

Result

The static IPv4 configuration of PC0 is verified using "ipconfig /all". The local TCP/IP stack and assigned host IP are tested using loopback and self-ping commands.

The lab is considered successful when both ping tests complete with 0% packet loss.

Conclusion

This lab demonstrates the configuration of static IPv4 addressing and the verification of local network interface settings using Cisco Packet Tracer and Command Prompt utilities.

Evidence

Screenshots of the following activities can be added to the repository:

1. Static IP Configuration
2. "ipconfig /all" Output
3. "ping 127.0.0.1" Output
4. "ping 192.168.10.25" Output
