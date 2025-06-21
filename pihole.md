# Guide to installing Pi=Hole on docker under proxmox

Key to note - the DNS resolution on the ProxMox host needs to be changed to allow for Pi-Hole to 'take-over' [port 53](https://docs.portainer.io/start/install-ce/server/docker/linux#deployment)

- Here is the main github for [Pi-Hole](https://github.com/pi-hole/docker-pi-hole)
- And this is the documentation for setup with [Docker](https://docs.pi-hole.net/docker/)

NOTE: Many of the Portainer templates, etc. for PiHole use the old version (v2 not V3) and do not work and there have been breaking changes since they were written
