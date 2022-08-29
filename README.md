# Boring VPN
A VPN that implements various encaspulation methods to create a tunnel regardless of network restrictions.

## Plan
- Start with simple, high bandwidth, low latency (i.e. bog standard wireguard). Progressively get more 'sneaky', and as a result lower throughput.
- Underlying VPN tunnel is wireguard.
- Encapsulate Wireguard in various firewall bypass techniques
   - Unordered ideas for encapsulation:
    - DNS Tunneling
    - NTP Tunneling (?)
    - OBFS4
    - Azure/AWS as a middleman (see tor 'meek' bridges)
    - MAC Spoofing (detect when an authorised device goes offline, and steal the MAC?)
    - ICMP Tunneling?
    - SSH Tunneling (would this even help?)
    - Check for TOR snowflake nodes, use them as 'exit points' (maybe possible on some large networks?)
    - Other Pluggable transports (https://obfuscation.github.io/)

- The idea is that every avenue of 'network escape' that can be automated would be tried. Try to hide the payload in **any** protocol that is allowed internet access.

## later plans.

- Use compression to increase throughput of slow transport methods.
- Possibly combine multiple tunneling methods to spread traffic and further avoid detection due to unnaturally large protocol traffic.
