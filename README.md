# ssltime
Advanced pcap analysis with tshark and bash.
## Usage
```
./ssltime [pcap file] [latency threshold]
```
## Example
Show SSL connections with more than one second between ClientHello and ServerHello.
```
$ ./ssltime my.pcap 1
Stream Time Source
168 5.001915 104.156.90.38
290 5.002695 23.235.43.44
304 5.002115 104.156.90.32
$
```
Then use the display filter `tcp.stream eq 304` to view the stream in wireshark.
## Motivation
I recently had the need to diagnose slow SSL handshakes to an F5 load balancer. A five second gap between ClientHello and ServerHello was plaguing 0.5% of connections.
