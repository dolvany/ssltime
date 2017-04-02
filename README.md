# ssltime
Advanced pcap analysis with tshark and bash.
## Usage
```
./ssltime [pcap file] [latency threshold (ms)]
```
## Example
Show SSL connections with more than 1000ms between ClientHello and ServerHello.
```
$ ./ssltime my.pcap 1000
Analyzing Pcap...
Stream Time Source
168 5001.915ms 104.156.90.38
290 5002.695ms 23.235.43.44
304 5002.115ms 104.156.90.32
$
```
Use a latency threshold of `0` to see all rows. Use the display filter `tcp.stream eq 304` to view the stream in wireshark.
## Motivation
I recently had the need to diagnose slow SSL handshakes to an F5 load balancer. A five second gap between ClientHello and ServerHello was plaguing 0.5% of connections.
