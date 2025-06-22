# Homelab
Information on the design and build of a homelab

## Key components
### Hardware
- Bee-link Mini EQR 5825 minipc with 32GB RAM and two M.2 drives - for running virtual machines on ProxMox
- Bee-link mini me - for running TrueNAS
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
