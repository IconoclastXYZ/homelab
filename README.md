# Homelab
Information on the design and build of a homelab

## Key components
### Hardware
- Bee-link Mini EQR 5825 minipc with 32GB RAM and two M.2 drives - for running virtual machines on ProxMox
- Bee-link mini me - for running TrueNAS
- [Minisforum MS-01](/minisforum_ms01.md)
  
### Software
#### Virtual machine server
- [ProxMox](/proxmox.md) - bare metal hypervisor
- [Docker](/docker.md) - VM host
- [Portainer](/portainer.md) - Docker control panel
- [Immich](/immich.md) - self-hosting photo library
- [Pi-Hole](/pihole.md) - DNS filtering
- [Tailscale](/tailscale.md) - secure remote access
- [IT-Tools](https://it-tools.tech) - great collection of commonly used tools

####
- Good series on the whole setup, including Traefik and authentik, reverse proxy servers, etc.
- [v1](https://www.simplehomelab.com/traefik-v3-docker-compose-guide-2024/), the link is to the Traefik config, but the whole series is there
- [v2](https://www.simplehomelab.com/ultimate-docker-media-server-udms-01/), which is not yet complete, but check it first

- [Intro to Traefik v3 with free certs](https://technotim.live/posts/traefik-3-docker-certificates/)

- [Intro video for tinyauth](https://www.youtube.com/watch?v=qmlHirOpzpc), which is good for single user access to a remote network, with the actual project [here](https://tinyauth.app)

- [Jim's garage](https://www.youtube.com/@Jims-Garage), has a nice series of articles on Homeab, Proxmox, tinyauth and hardware too

Remember that after you have created a new VM or LXC you need to [enable qemu quest services](https://pve.proxmox.com/wiki/Qemu-guest-agent) so that ProxMox can get notifications from the VM and also shut it down gracefully

#### NAS
- [TrueNAS](/truenas.md)
- Pi-Hole (backup)

### External access
There are quite a few different ways to skin this cat:
- Open ports 80 & 443 (as in the v1 and v2 guides above) - not ideal, can still check passwords, etc using tinyauth or authentik, etc.
- VPN - great for a single user, but not good if you want anything publically exposed
- Cloudflared tunnel - good guide [here](https://mattdyson.org/blog/2024/02/using-traefik-with-cloudflare-tunnels/) on how to put many of these pieces together! [This one](https://homelamb.github.io/posts/using-cloudflare-tunnel-with-traefik/) also gives some more details
- tailscale - good for access from pre-defined/connected endpoints - mentioned a few times above

### Service monitoring
- Can use something like [Checkmate](https://www.youtube.com/watch?v=yCnkkljii_k)

### Building a Smart Home
- Using [Home Assistant](https://www.youtube.com/watch?v=6z-ilfbzDlY) and HACS
- Need to work out how to get data off an ESP32 onto it... with some methods [here](https://randomnerdtutorials.com/esp32-how-to-log-data/)

