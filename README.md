# Homemade Ad Blocker with Raspberry Pi

> A comprehensive guide to building a network-level ad blocker using a Raspberry Pi, Pi-hole, and Tailscale to block ads on all devices, anywhere.

This project explains how to deploy a DNS sinkhole (Pi-hole) at home and access it securely from anywhere using a Tailscale VPN. It ensures that devices on mobile data or public WiFi can still benefit from network-level ad blocking without draining battery or compromising privacy.

## Features

- **Network-Level Ad Blocking:** Blocks ads and trackers across all apps, not just web browsers.
- **Global Reach:** Uses Tailscale to enforce Pi-hole DNS on mobile devices and laptops regardless of physical location.
- **Aggressive Blocklists:** Integrated with optimized blocklists stopping over 7 million malicious and tracking domains.
- **Exit Node Routing:** Optionally routes all internet traffic through the home network for secure browsing on public WiFi.
- **MagicDNS Support:** Access local services using easy-to-remember hostnames instead of IP addresses.

## Architecture

A Raspberry Pi runs Pi-hole (port 53) and the Tailscale daemon. All devices (phones, laptops) connect to the Tailscale private network (tailnet). The Tailscale admin console is configured to override local DNS and force all tailnet devices to query the Raspberry Pi's Tailscale IP (`100.x.x.x`) for DNS resolution.

## Tech Stack

- **Hardware:** Raspberry Pi (Debian 13 "Trixie")
- **DNS Server:** Pi-hole
- **VPN:** Tailscale (WireGuard)

## Getting Started

### Prerequisites

- A Raspberry Pi running Debian/Raspberry Pi OS.
- A free Tailscale account.
- Basic familiarity with SSH and Linux command line.

### Installation

1. **Install Pi-hole:**
   ```bash
   curl -sSL https://install.pi-hole.net | bash
   ```
2. **Install Tailscale:**
   ```bash
   curl -fsSL https://tailscale.com/install.sh | sh
   sudo tailscale up
   ```
3. **Configure Devices:**
   Install Tailscale on your mobile and laptop devices and join the same tailnet.
4. **Enforce DNS:**
   In the Tailscale admin console, set the Raspberry Pi's `100.x.x.x` IP as a Global Nameserver and enable "Override local DNS".

## Usage

- Devices connected to Tailscale will automatically drop ad requests into the sinkhole.
- You can access the Pi-hole admin interface remotely at `http://<raspberry-tailscale-ip>/admin`.
- Monitor logs in real-time on the Raspberry Pi: `tail -f /var/log/pihole/pihole.log`

## License

This project is licensed under the MIT License.
