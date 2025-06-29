# Guide for setting up docker within ProxMox

After far too much research, use a VM not an LXC for Docker, at least for now

Use an Ubuntu VM - once again, too much research...

Several good guides are around, with [this one](https://www.xda-developers.com/use-docker-with-proxmox/) quite useful and [this](https://www.naturalborncoder.com/2023/07/installing-docker-and-portainer-on-a-proxmox-vm/)

[This video](https://www.youtube.com/watch?v=wrlukx-QYRw) goes through how to install docker and portainer as well

- Docker convenience script for [Debian](https://docs.docker.com/engine/install/debian/) - made it very easy

Post installation steps for Docker
- [Runnings as a non-root user](https://docs.docker.com/engine/install/linux-postinstall/)

Resizing a partition
- After using the tools in ProxMox
- https://kayg.org/notes/enlarge-disk-proxmox-vm
