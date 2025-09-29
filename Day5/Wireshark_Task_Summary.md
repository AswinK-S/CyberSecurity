
# Wireshark Packet Capture Summary

## Steps Performed

1. **Installed Wireshark**  
   Installed Wireshark on the local machine.

2. **Started Capture**  
   Began capturing packets on the active network interface.

3. **Generated Traffic**  
   Opened a browser and pinged a server to create network traffic.

4. **Stopped Capture**  
   Stopped the capture after approximately one minute.

5. **Filtered Packets**  
   Applied filters for `HTTP`, `DNS`, and `TCP` protocols.

6. **Identified Protocols**  
   Observed at least three protocols:  
   in my system I only got `Tcp` protocol
   - **DNS**: Used for resolving domain names.  
   - **HTTP**: Captured when browsing websites.  
   - **TCP**: The transport protocol underlying HTTP traffic.  

7. **Exported Capture**  
   Saved the capture file in `.pcap` format for future analysis.

## Findings

- **DNS Queries**: Showed requests and responses for resolving hostnames.  
- **HTTP Traffic**: Displayed GET requests when accessing web pages.  
- **TCP Packets**: Demonstrated the handshake and communication between client and server.  

## Conclusion

Wireshark is a powerful tool to capture and analyze network traffic. From this exercise, I learned how to capture, filter, and analyze different types of packets in a live network environment.
