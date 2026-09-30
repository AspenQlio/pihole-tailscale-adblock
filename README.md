# Secure DNS and Adblocking via Split-Tunnel VPN

> **[Español] → La documentación completa, con instalación paso a paso y los errores que me encontré, está en [README.es.md](README.es.md).**

This project documents the deployment of a network-wide DNS sinkhole (Pi-hole) securely accessible from any external network via a mesh VPN (Tailscale).

## Problem
Mobile devices and laptops lose network-level adblocking and malware filtering as soon as they disconnect from the home Wi-Fi. Exposing the DNS resolver to the public internet via port forwarding is a severe security risk.

## Solution
By overlaying Tailscale on top of the Pi-hole instance, the Pi-hole becomes the authoritative DNS server for the Tailscale network (Tailnet). Devices use a split-tunnel configuration where only DNS requests route to the home network, while standard traffic goes directly to the internet.

- **Zero Port Forwarding:** The home router remains completely closed.
- **Global Adblocking:** Mobile devices route DNS queries to the sinkhole over a WireGuard-backed encrypted tunnel.
- **Battery Efficient:** Split-tunneling avoids the overhead of routing heavy data traffic through the home connection.
