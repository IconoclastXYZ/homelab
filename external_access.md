## Proxmox with traefik and cloudflare, even using authentik
- Open ports 80 & 443 (as in the v1 and v2 guides above) - not ideal, can still check passwords, etc using tinyauth or authentik, etc.
- VPN - great for a single user, but not good if you want anything publically exposed
- Cloudflared tunnel - good guide [here](https://mattdyson.org/blog/2024/02/using-traefik-with-cloudflare-tunnels/) on how to put many of these pieces together! [This one](https://homelamb.github.io/posts/using-cloudflare-tunnel-with-traefik/) also gives some more details
- tailscale - good for access from pre-defined/connected endpoints - mentioned a few times above

Using Traefik with Cloudflare Tunnels - based on Docker containers. Very good walk through
https://mattdyson.org/blog/2024/02/using-traefik-with-cloudflare-tunnels/

Complete Setup Guide: Traefik + Cloudflare Tunnel on Proxmox LXC
https://github.com/sfnemis/proxmox-traefikproxy-cloudflaretunnel

Authentik Docker Compose Guide with Traefik 2025 (with authentik)
https://www.simplehomelab.com/authentik-docker-compose-guide-2025/

and by the same person
Proxmox Web UI Behind Traefik Reverse Proxy: ✅ The Right Way
https://www.youtube.com/watch?v=ldytlKJmPX4

## How to setup Traefik with Cloudflare in a LXC instead of Docker
Not sure that it is a good idea, but here it is anyway

https://portal.habitats.tech/Traefik-Proxy+3.x/Traefik-Proxy+3.x+-+Install

https://portal.habitats.tech/Traefik-Proxy+3.x/Traefik-Proxy+3.x+-+Setup

## RDP in Debian - giving you another way to reach the network
[How to setup RDP in Debian](https://phoenixnap.com/kb/debian-remote-desktop)

## VPN with an exit node on the local network
[Using Cloudflar WARP, MASQUE and Dante SOCKS5 server](https://www.youtube.com/watch?v=oiqc5xbNmks) with a [Reddit thread](https://www.reddit.com/r/unRAID/comments/14qlay6/cloudflare_tunnel_as_a_exit_node/) on exit nodes on Cloudflare
[Using Tailscale](https://tailscale.com/kb/1103/exit-nodes) and a [Reddit thread](https://www.reddit.com/r/Tailscale/comments/1e8rw88/tailscale_travel_router_setup/) on how to use a travel router (eg. [Beryl AX](https://www.gl-inet.com/products/gl-mt3000/) to provide secure reachback when using a shared network

