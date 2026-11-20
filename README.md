# boxings

boxings is a network proxy inspired by singbox, but gc(letter gs) stays at the edge, built for low-RAM, low-flash devices such as routers.

## TUN

TUN stack modes:

| Mode | TCP | UDP |
| --- | --- | --- |
| `mixed` (default) | System listener with packet NAT | User-space UDP datagram transport |
| `system` | System listener with packet NAT | Direct packet parsing and UDP sessions |

## Platform support

Only implemented parts are listed.

| Component | Direction | Linux | Windows |
| --- | --- | --- | --- |
| `direct` | inbound, outbound | TCP, UDP | TCP, UDP |
| `redirect` | inbound | TCP | Not available |
| `tproxy` | inbound | TCP, UDP | Not available |
| `tun` | inbound | TCP, UDP (user-space stack) | TCP, UDP (Wintun + user-space stack) |
| `vless` | inbound, outbound | TCP; UDP plain, packetaddr, XUDP; TLS, REALITY, Vision, WebSocket | TCP; UDP plain, packetaddr, XUDP; TLS, REALITY, Vision, WebSocket |
| `socks` | inbound, outbound | SOCKS4/4a/5 TCP; SOCKS5 UDP ASSOCIATE | SOCKS4/4a/5 TCP; SOCKS5 UDP ASSOCIATE |
| `http` | inbound | TCP proxy | TCP proxy |
| `mixed` | inbound | TCP; HTTP and SOCKS4/5 detection | TCP; HTTP and SOCKS4/5 detection |

## Examples

- `examples/redirect` — REDIRECT with route-stage HTTP/TLS sniffing
- `examples/tproxy` — TPROXY configuration
- `examples/tun` — TUN configuration
