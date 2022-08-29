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
    - https://github.com/blanu/Dust
    - Other Pluggable transports (https://obfuscation.github.io/)

- The idea is that every avenue of 'network escape' that can be automated would be tried. Try to hide the payload in **any** protocol that is allowed internet access.

## later plans - these should be investigated after the initial plan is complete.

- Use compression to increase throughput of slow transport methods.
- Possibly combine multiple tunneling methods to spread traffic and further avoid detection due to unnaturally large protocol traffic.
- Refraction Networking - https://refraction.network/
   - Assume the network allows access to one specific domain, refraction networking could be implemented if the ISP supports it.
- For extremely slow connections, possibly implement a simple Client -> Server ASCII message system as a 'last ditch' comms method.
   - This could be useful for things like pen-testing. Where you need to get a message to someone outside.
   - even at **extremely** low bandwidth, a simple ASCII message could be passed over a TCP tunnel.
   - This could be taken further and implement an entire Client -> Server stealth communication suite via the heavily obfuscated tunnel.
