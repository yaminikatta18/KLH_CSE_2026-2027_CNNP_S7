# Skill 2: Three-Point Capture

## Experiment Overview
Captured network traffic simultaneously at three points (`host1` on `veth-h1`, `router` on `veth-r1`, and `host2` on `veth-h2`) while transmitting TCP messages on port `1234` with `netem` configured for `20ms` delay and `1%` packet loss on `veth-r2`.

## Analysis Results

### 1. TTL Decrement Across Capture Points
- **`cap1.pcap` (`host1` - `veth-h1`):** `7` packets with TTL `64` (outbound), `5` packets with TTL `63` (inbound return traffic)
- **`cap2.pcap` (`router` - `veth-r1`):** `7` packets with TTL `64`, `5` packets with TTL `63`
- **`cap3.pcap` (`host2` - `veth-h2`):** `6` packets with TTL `63` (decremented by 1 at `router`), `5` packets with TTL `64` (outbound replies from `host2`)

### 2. Transmitted TCP Message Payload (`tcp.port == 1234`)
```text
Hello from host1!
This is Yamini
Computer Networks Lab
Three Point Capture Experiment
