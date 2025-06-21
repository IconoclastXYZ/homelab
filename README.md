# Homelab
Information on the design and build of a homelab

## Key components
### Hardware
- Bee-link Mini EQR 5825 minipc with 32GB RAM and two M.2 drives - for running virtual machines on ProxMox
- Bee-link mini me - for running TrueNAS
### Software
#### Virtual machine server
- [ProxMox](/proxmox.md)
- Docker
- Portainer
- Immich
- Pi-Hole

Remember that after you have created a new VM or LXC you need to [enable qemu quest services](https://pve.proxmox.com/wiki/Qemu-guest-agent) so that ProxMox can get notifications from the VM and also shut it down gracefully

#### NAS
- TrueNAS
- Pi-Hole (backup)
