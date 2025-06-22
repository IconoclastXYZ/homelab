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

Remember that after you have created a new VM or LXC you need to [enable qemu quest services](https://pve.proxmox.com/wiki/Qemu-guest-agent) so that ProxMox can get notifications from the VM and also shut it down gracefully

#### NAS
- [TrueNAS](/truenas.md)
- Pi-Hole (backup)
