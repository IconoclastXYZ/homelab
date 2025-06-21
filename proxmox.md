# ProxMox Build Guide

In no particular order for now...

## Some video walkthroughs on getting the whole thing working
- [Homelab Setup Guide - Proxmox / TrueNAS / Docker Services](https://www.youtube.com/watch?v=yDkc3D3BFhM)
- [the ULTIMATE Home Server Setup - Full Walkthrough Guide Pt.1 (Proxmox, ZFS, Samba)](https://www.youtube.com/watch?v=qmSizZUbCOA&t=162s)
- [So, you want to start self-hosting? Part 1 - How to install Proxmox and pick your hardware.](https://www.youtube.com/watch?v=zngSuqCM4d8&t=657s), who also talks about TailScale for remote access and networking
- [Complete beginners guide to self-hosting | Part 2 Installing Immich, Audiobookshelf + Home Assistant](https://www.youtube.com/watch?v=guHoZ68N3XM), noting that some parts are overly simplified, such as not using two disks for ProxMox and how to link external volumes for Immich

## Scripts to run post installation
- [here](https://www.xda-developers.com/proxmox-scripts-run-new-installation/)

## Setup email notifications
This requires the setup of an SMTP relay since this is a Linux box and wants to send out to the real world. I could have used gmail, but I want to send using my own domain

Main steps:
- Get a domain
- Host its DNS on Cloudflare.com
- Setup the DNS records for mail
- Setup a free acount on Mailjet.com
- Setup domain wide forwarding

All of these steps are well described [here](https://franzramadhan.dev/blog/01-free-own-domain-email-using-cloudflare-mailjet/)

Once it is all setup then the final changes need to be made in ProxMox in the Datacenter Notifications section as outlined [here](https://blog.programster.org/configure-proxmox-smtp-for-email-notifications)

## Setup UPS notifications and shutdown control
- Use a [Synology NAS](https://www.reddit.com/r/synology/comments/gtkjam/use_synology_nas_as_ups_server_to_safely_power/) as the UPS server
- Setup [ProxMox](https://www.reddit.com/r/Proxmox/comments/kj18v8/how_to_verify_that_nut_driver_is_really_working/) as the client and confirm that it is working

## Suggested LXCs to make life easier
- [here are 7 to start with](https://www.xda-developers.com/proxmox-lxcs-i-couldnt-live-without/)
- 
