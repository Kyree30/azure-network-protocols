<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Download WireShark
- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DHCP Traffic
- Observe DNS Traffic
- Observe RDP Traffic

<h2>Actions and Observations</h2>
<b>Download WireShark</b>
<p>
<img src="https://i.imgur.com/WSTgTMb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p><b>
  Within your Windows 10 Virtual Machine, Install Wireshark</b>
</p>
<br />

<p>
<img src="https://i.imgur.com/ckVd2MU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/CZc33lM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/djm7CxJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p><b>
1. Open Wireshark and filter for ICMP traffic only
Retrieve the private IP address of the Ubuntu VM and attempt to ping it from within the Windows 10 VM
2. Observe ping requests and replies within WireShark
3. From The Windows 10 VM, open command line or PowerShell and attempt to ping a public website (such as www.google.com) and observe the traffic in WireShark
</b>
</p>
<br />

<p>
<img src="https://i.imgur.com/VXJk1Rc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/M1S0StN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/VxE3U46.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p><b>
1.Back in Wireshark, filter for SSH traffic only
2.From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address)
3.Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark
4.Exit the SSH connection by typing ‘exit’ and pressing [Enter]
</b>
</p>
<br />

<p>
<img src="https://i.imgur.com/J2daKah.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p><b>
1.Back in Wireshark, filter for DHCP traffic only
2.From your Windows 10 VM, attempt to issue your VM a new IP address from the command line (ipconfig /renew)
  3.Observe the DHCP traffic appearing in WireShark</b>
</p>
<br />

<p>
<img src="https://i.imgur.com/qGTucWv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p><b>
1.Back in Wireshark, filter for DNS traffic only
2.From your Windows 10 VM within a command line, use nslookup to see what google.com and disney.com’s IP addresses are
  3.Observe the DNS traffic being show in WireShark</b>
</p>
<br />

<p>
<img src="https://i.imgur.com/77EjsER.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p><b>
1.Back in Wireshark, filter for RDP traffic only (tcp.port == 3389)
2.Oserve the immediate non-stop spam of traffic? Why do you think it’s non-stop spamming vs only showing traffic when you do an activity?
3. Answer: because the RDP (protocol) is constantly showing you a live stream from one computer to another, therefor traffic is always being transmitted</b>
</p>
<br />
