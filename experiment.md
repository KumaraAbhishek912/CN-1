# Laboratory Experiment: Study of Network Devices and LAN Configuration

## Aim
To study network devices in detail and connect computers in a Local Area Network (LAN).

## Problem statement
Study the functions of a NIC, repeater, hub, switch, bridge, router, and gateway. Connect at least three computers through an Ethernet switch, configure IPv4 addresses, and test connectivity with `ping`.

## Apparatus / requirements
- Three or more computers with Ethernet NICs
- Ethernet switch
- Cat5e/Cat6 Ethernet cables with RJ45 connectors
- Windows or Linux operating system
- Command Prompt or Terminal
- Optional router for Internet access

## Theory

### 1. Network Interface Card (NIC)
A NIC provides a network interface that allows a computer to send and receive data over a wired or wireless network.

### 2. Repeater
A repeater works at the Physical Layer (Layer 1) of the OSI model. It regenerates or retimes signals to extend the distance over which a signal can travel.

### 3. Hub
A hub is a multiport repeater that works at the Physical Layer (Layer 1). It repeats incoming signals to the other ports rather than forwarding frames selectively by MAC address. Hubs are largely obsolete in modern Ethernet LANs.

### 4. Switch
A typical Ethernet switch works at the Data Link Layer (Layer 2). It learns source MAC addresses and forwards frames to the relevant port when it knows the destination port. Layer 3 switches can also route IP packets.

### 5. Bridge
A bridge connects LAN segments and filters/forwards frames based on MAC addresses. It typically works at the Data Link Layer (Layer 2). A switch is often described as a multiport bridge.

### 6. Router
A router connects different IP networks and forwards packets using destination IP addresses and routing information. Its core function operates at the Network Layer (Layer 3).

### 7. Gateway
A gateway connects systems or networks and may translate between different protocols or data formats. In a normal IP LAN, the default gateway is usually the router used to reach destinations outside the local subnet.

## Procedure

### Part A — Study network devices
1. Study the purpose of each device described in the theory section.
2. Identify the OSI layer at which each device typically operates.
3. Compare how hubs, switches, bridges, and routers handle traffic.

### Part B — Connect the LAN
1. Connect PC1, PC2, and PC3 to separate ports on the Ethernet switch.
2. Power on the switch and computers.
3. Check the Ethernet link/activity LEDs.
4. Confirm that the Ethernet adapters are enabled.

### Part C — Configure IPv4
Use the following example address plan, provided these addresses are not already in use on the network.

| Computer | IPv4 address | Subnet mask | Default gateway |
|---|---|---|---|
| PC1 | `192.168.1.10` | `255.255.255.0` | Blank for isolated LAN |
| PC2 | `192.168.1.11` | `255.255.255.0` | Blank for isolated LAN |
| PC3 | `192.168.1.12` | `255.255.255.0` | Blank for isolated LAN |

For Windows:
1. Open Control Panel.
2. Go to Network and Sharing Center.
3. Select Change adapter settings.
4. Right-click Ethernet and choose Properties.
5. Select Internet Protocol Version 4 (TCP/IPv4), then Properties.
6. Select “Use the following IP address” and enter the appropriate address and subnet mask.
7. Leave the default gateway blank if the LAN is isolated. If a router is present, enter its actual LAN IP address.
8. Save the settings.

### Part D — Verify connectivity
On each Windows computer, open Command Prompt.

Run:
```bat
ipconfig
```

From PC1, test PC2 and PC3:
```bat
ping 192.168.1.11
ping 192.168.1.12
```

From PC2, test PC1:
```bat
ping 192.168.1.10
```

Record whether replies were received and note packet loss. Save screenshots of the real command output in the repository's `outputs/` folder.

## Expected output
The `ipconfig` command should display each computer's configured IPv4 address and subnet mask. Successful ping tests should show replies from the destination and report packet statistics. Actual output may vary.

## Troubleshooting
- Verify cable connections and switch link LEDs.
- Check that the computers are on the same subnet and have unique IP addresses.
- Check adapter status and firewall settings. A firewall can block ICMP echo requests.
- Confirm that the selected addresses do not conflict with other devices.
- A default gateway is not required for communication between hosts in the same subnet.

## Result
The network devices are studied, and a LAN can be established by connecting computers to a switch, assigning appropriate IP addresses, and verifying communication using `ping`. Enter the actual observed results below.

| Test | Actual result |
|---|---|
| PC1 → PC2 (`ping 192.168.1.11`) | To be filled after testing |
| PC1 → PC3 (`ping 192.168.1.12`) | To be filled after testing |
| PC2 → PC1 (`ping 192.168.1.10`) | To be filled after testing |
