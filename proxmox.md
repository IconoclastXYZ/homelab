# ProxMox Build Guide

In no particular order for now...

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

