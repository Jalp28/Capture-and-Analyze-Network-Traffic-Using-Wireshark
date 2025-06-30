# Packet Analysis with Wireshark on a Personal Network

This guide walks you through performing a basic packet analysis on your personal network using Wireshark, a free and open-source packet analyzer. Follow the steps to capture, filter, and analyze network traffic, then document your findings.

### Steps to Perform Packet Analysis

1. **Install Wireshark**:
   - Download Wireshark from the official website: [https://www.wireshark.org/download.html](https://www.wireshark.org/download.html).
   - Choose the version for your operating system (Windows, macOS, or Linux) and follow the installation instructions.
   - Launch Wireshark after installation to verify it’s working.

2. **Start Capturing on Your Active Network Interface**:
   - Open Wireshark and select your active network interface (e.g., Wi-Fi or Ethernet) from the interface list.
   - Click "Start" to begin capturing packets in real-time.
   - Note: Ensure you have administrative privileges to capture traffic.

3. **Browse a Website or Ping a Server to Generate Traffic**:
   - Open a browser and visit a website (e.g., [https://www.example.com](https://www.example.com)) or use the command line to ping a server (e.g., `ping google.com`).
   - Perform this action for about 30-60 seconds to generate sufficient traffic.

4. **Stop Capture After a Minute**:
   - Return to Wireshark and click "Stop" (red square button) after approximately one minute of capture.
   - Review the initial packet list to ensure traffic was recorded.

5. **Filter Captured Packets by Protocol**:
   - Use Wireshark’s filter bar to apply protocol filters:
     - Type `http` to view HTTP traffic.
     - Type `dns` to view DNS queries.
     - Type `tcp` to view TCP packets.
     - Type `icmp` to view ICMP packets.
   - Apply the filter and press Enter to narrow down the packet list.

6. **Identify at Least 3 Different Protocols in the Capture**:
   - Analyze the filtered packets to identify protocols. Common examples include:
     - **HTTP**: Web browsing traffic (e.g., packets to/from port 80).
     - **DNS**: Domain name resolution (e.g., packets to/from port 53).
     - **TCP**: Transmission control protocol (e.g., handshake packets on various ports).
     - **ICMP**: Ping and network diagnostic traffic (e.g., Echo Request/Reply packets to/from destinations like 8.8.8.8).
   - Right-click a packet, select "Protocol Hierarchy," and review the statistics for confirmation.

7. **Export the Capture as a .pcap File**:
   - Go to `File > Save As` in Wireshark.
   - Choose a location, name the file (e.g., `network_capture.pcap`), and save it as a `.pcap` file.
   - This file can be reopened later for further analysis or shared (anonymized) for reference here I uploaded mine for reference.

8. **Summarize Your Findings and Packet Details**:
   - Review the capture and note key observations:
     - **HTTP**: Requests to `google.com` with GET methods, showing webpage loading.
     - **DNS**: Queries to resolve `google.com` to an IP (e.g., 93.184.216.34), indicating name resolution.
     - **TCP**: Handshake packets (SYN, SYN-ACK, ACK) on ports like 80 or 443, ensuring reliable data transfer.
     - **ICMP**: Echo Request and Echo Reply packets to/from 8.8.8.8, indicating successful ping operations for network diagnostics.
   - Example Summary: Captured 500 packets, including 100 HTTP requests, 20 DNS queries, and 300 TCP packets over 1 minute.

### Additional Guidelines and Best Practices

- **Secure Your Capture**:
  - Avoid capturing sensitive data (e.g., passwords); use HTTPS websites or a test environment.
  - Anonymize `.pcap` files before sharing by removing personal IPs or credentials.

- **Analyze Traffic Patterns**:
  - Look for anomalies like excessive DNS requests or unexpected ports, which may indicate malware or misconfiguration.

- **Learn Advanced Filters**:
  - Explore filters like `ip.addr == 192.168.1.1` to focus on specific IPs or `tcp.port == 443` for HTTPS traffic.
  - Refer to the Wireshark Filter Reference: [https://www.wireshark.org/docs/man-pages/](https://www.wireshark.org/docs/man-pages/).

- **Regular Monitoring**:
  - Schedule periodic captures to monitor network health over time.
  - Use Wireshark’s "Statistics" menu for detailed traffic analysis.

### Contributing

- Suggestions for additional protocols or analysis techniques are welcome! Open an issue or submit a pull request.
- Please anonymize any shared `.pcap` files to protect privacy.


> **Disclaimer**: This guide is for educational purposes only. Capture traffic with proper authorization to comply with legal and ethical standards.
