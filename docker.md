## Guide for setting up docker within ProxMox

After far too much research, use a VM not an LXC for Docker, at least for now

Use an Ubuntu VM - once again, too much research...

Several good guides are around, with [this one](https://www.xda-developers.com/use-docker-with-proxmox/) quite useful and [this](https://www.naturalborncoder.com/2023/07/installing-docker-and-portainer-on-a-proxmox-vm/)

[This video](https://www.youtube.com/watch?v=wrlukx-QYRw) goes through how to install docker and portainer as well

- Docker convenience script for [Debian](https://docs.docker.com/engine/install/debian/) - made it very easy

Post installation steps for Docker
- [Running as a non-root user](https://docs.docker.com/engine/install/linux-postinstall/)

Resizing a partition
- After using the tools in ProxMox
- https://kayg.org/notes/enlarge-disk-proxmox-vm

## What directory structure to use
- Start with a non-privileged user in the docker group, eg. debian
- New directory for each machine
```
.
└── debian/
    ├── traekif/
    │   ├── Dockerfile
    │   ├── compose.yaml
    │   ├── compose.override.yaml
    │   └── app_directory/
    │       ├── other_files
    │       └── more_files
    └── immich/
        ├── Dockerfile
        ├── compose.yaml
        ├── compose.override.yaml
        ├── .env
        ├── upload/
        │   └── uploaded images
        └── pgdata/
            └── data files
```
- Diagram created [with](https://tree.nathanfriend.com/)

## Mouting external drives in Docker machines
- Mount it to the Docker VM host filesystem - https://askubuntu.com/questions/101029/how-do-i-mount-a-cifs-share
- Then need to change fstab to make it persistent / reload on restart
- Some details here - https://unix.stackexchange.com/questions/469274/debian-server-auto-mount-samba-share
- and here - https://www.naturalborncoder.com/2023/07/mounting-a-samba-share-under-debian/

- Final entry into fstab is: //192.168.1.2/Photos /mnt/photos cifs credentials=/home/debian/.DS918_smbcredentials,vers=3.0,uid=debian,gid=docker,ro,noauto,noperm,x-systemd.automount 0 0

- Then mount it as a volume inside the machine - https://forums.docker.com/t/docker-compose-mount-samba-volume/132407
- More about Docker volumes here - https://docs.docker.com/engine/storage/volumes/
- Storage mount options - https://docs.docker.com/engine/storage/
