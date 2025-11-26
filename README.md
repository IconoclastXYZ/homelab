# Homelab
Information on the design and build of a homelab

## Key components
### Hardware
- Bee-link Mini EQR 5825 minipc with 32GB RAM and two M.2 drives - for running virtual machines on ProxMox
- Bee-link mini me - for running TrueNAS
- [Minisforum MS-01](/minisforum_ms01.md)
- Changing the IP Address of a machine is now done with NetPlan and creating an new .yaml file. nmcli does not work
  
### Software
#### Virtual machine server
- [ProxMox](/proxmox.md) - bare metal hypervisor, with lots of [helper scripts](https://community-scripts.github.io/ProxmoxVE/) and a guide to managing storage [here](https://github.com/TechHutTV/homelab/blob/main/storage/README.md)
- [Docker](/docker.md) - VM host
- [Portainer](/portainer.md) - Docker control panel
- [Immich](/immich.md) - self-hosting photo library
- DNS filtering with [Pi-Hole](/pihole.md) or perhaps [Technitium](/technitium.md) which looks more versatile or [Adguard](/adguard.md) which overall is probably easier to manage and powerful enough
- [Tailscale](/tailscale.md) - secure remote access
- [IT-Tools](https://it-tools.tech) - great collection of commonly used tools
- [HomePage](/homepage.md) - great YAML based homepage tool in Docker
- [Authentik](/authentik.md) - for authentication
- [NGX Proxy Manager]() - for a local proxy and access its logs [here](https://thomaswildetech.com/blog/2025/01/31/using-goaccess-with-nginx-proxy-manager-npm-to-visuallize-logs/)

- With some to consider for later
- [HomeAssistant](https://www.wundertech.net/how-to-set-up-home-assistant-on-proxmox/) - how to get it running on ProxMox
- [Mailrise](https://github.com/YoRyan/mailrise) for SMTP to arrise gateway and modern notifications
- [Open Archiver](https://openarchiver.com/) for email archives to be locally hosted and searchable
- [Vert](https://github.com/VERT-sh/VERT) locally hosted file converter
- [Stirling PDF](https://docs.stirlingpdf.com/Installation/Docker%20Install/)

### Resources
- [Jim's garage](https://www.youtube.com/@Jims-Garage), has a nice series of articles on Homeab, Proxmox, tinyauth and hardware too

Remember that after you have created a new VM or LXC you need to [enable qemu quest services](https://pve.proxmox.com/wiki/Qemu-guest-agent) so that ProxMox can get notifications from the VM and also shut it down gracefully

#### NAS
- [TrueNAS](/truenas.md)
- Pi-Hole (backup)

### External access
The Security starts with using Cloudflare tunnels and then [Authentik](/authentik.md) using Nginx Proxy Manager.

(I looked at using Traefik, but it works best when everything is inside Docker)

Both Cloudflare tunnels and also Authentik can be set up to render an RDP session in the browser

A good guide on setting up RDP on Debian can be found [here] (https://phoenixnap.com/kb/debian-remote-desktop)

### Service monitoring and Uptime
- Can use something like [Checkmate](https://www.youtube.com/watch?v=yCnkkljii_k) for service monitoring
- Or Keepalived for robust service availability - https://www.xda-developers.com/keepalived-makes-home-network-resilient/
- And a Dashboard to keep an eye on it - https://www.xda-developers.com/this-is-the-only-dashboard-my-nas/

### Building a Smart Home
- Using [Home Assistant](https://www.youtube.com/watch?v=6z-ilfbzDlY) and HACS
- Need to work out how to get data off an ESP32 onto it... with some methods [here](https://randomnerdtutorials.com/esp32-how-to-log-data/)

### Getting the Motion library to work on a raspberry Pi
https://pimylifeup.com/raspberry-pi-webcam-server/

