# Wireshark Network Traffic Analysis Report

## Task Objective

Analyze the provided Wireshark packet capture (`wireshark.pcapng`) and
document the observed network traffic, protocols, and key findings.

## Capture Summary

-   **Total packets captured:** 6,457
-   **Capture duration:** Approximately 690.5 seconds (11.5 minutes)
-   **Main protocols observed:** TCP, UDP, DNS, ARP, HTTP, and HTTPS/TLS
-   **TCP packets identified:** 1,808
-   **UDP packets identified:** 159
-   **DNS packets identified:** 153
-   **ARP packets identified:** 20
-   **Traffic using TCP port 443:** 1,204 packets
-   **Traffic using TCP port 80:** 19 packets

## Protocol Analysis

### TCP

TCP was the most commonly observed transport protocol. A large amount of
TCP communication used destination or source port 443, indicating
encrypted HTTPS/TLS web traffic.

### UDP and DNS

The capture contained UDP traffic, with 153 packets associated with DNS.
DNS traffic was used to resolve domain names into IP addresses.

Some domains observed in DNS queries included: - `edge.microsoft.com` -
`clients4.google.com` - `c.pki.goog` - `www.msftconnecttest.com` -
`drive.google.com` - `www.google.com` - `acrobat.adobe.com` -
`www.bing.com` - `alive.github.com` - `ws.chatgpt.com`

### ARP

ARP packets were present in the capture. ARP is used on a local network
to map IP addresses to MAC addresses.

### HTTP and HTTPS/TLS

Only a small amount of traffic used TCP port 80, while significantly
more traffic used TCP port 443. This indicates that most observed web
communication was encrypted using HTTPS/TLS.

## Key Communication Observed

A frequently observed local communication pair was: - `10.172.149.254` ↔
`10.172.149.163`

Other external IP addresses were also contacted during the capture,
showing normal communication between the local system/network and
internet services.

## Key Findings

1.  The packet capture contains 6,457 packets collected over
    approximately 11.5 minutes.
2.  TCP is the dominant identified transport protocol.
3.  HTTPS/TLS traffic is significantly more common than unencrypted HTTP
    traffic.
4.  DNS queries show communication with services associated with
    Microsoft, Google, Adobe, GitHub, and other online platforms.
5.  ARP traffic indicates normal local-network address resolution
    activity.
6.  Based on this basic traffic analysis, the capture mainly shows
    routine network and internet communication. No conclusion about
    malicious activity should be made without deeper packet-level
    investigation and additional context.

## Useful Wireshark Display Filters

-   `tcp`
-   `udp`
-   `dns`
-   `arp`
-   `http`
-   `tls`
-   `tcp.port == 443`
-   `ip.addr == 10.172.149.254`

## Conclusion

The provided `wireshark.pcapng` file was analyzed to identify major
protocols and communication patterns. The capture mainly contains
TCP-based encrypted web traffic, DNS requests, UDP traffic, and ARP
activity. The analysis demonstrates how Wireshark packet captures can be
used to understand network behavior, identify protocols, inspect
endpoints, and investigate network communication.

## Files

-   `wireshark.pcapng` --- Original packet capture
-   `README.md` --- Network traffic analysis report
