# ssltime
Advanced pcap analysis with tshark and bash.
## Usage
```
$ ./ssltime
Usage: ./ssltime [pcap file] [min latency (ms)]
$
```
## Example
Show connections with an SSL handshake time greater than 1000ms.
```
$ ./ssltime my.pcap 1000
Analyzing Pcap...
Stream Time Source
168 5047.552ms 104.156.90.38
290 5228.129ms 23.235.43.44
304 5048.646ms 104.156.90.32
3 Rows
$
```
Use a min latency of `0` to see all rows. Use a display filter of `tcp.stream eq 304` to view the stream in wireshark.
## Motivation
I recently had the need to diagnose slow SSL handshakes to an F5 load balancer. A five second gap between ClientHello and ServerHello was plaguing 0.5% of connections.
