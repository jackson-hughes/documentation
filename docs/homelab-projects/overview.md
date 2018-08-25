# Homelab Overview

## Technologies

*   Hypervisor / virtualisation: Kernel Kirtual Machines (KVM)
*   Storage / NAS: FreeNAS
    1.  Backups
        *   Time machine backups for macbooks
        *   SMB share for Windows clients
        *   NFS share for Linux clients
        *   Currently, no VM filesystems are backed up; ZFS takes care of that at the host level.


## Services

### Plex Media Server

### Confluence

I no longer self-host an Atlassian Confluence instance. It was used solely for documentation which has now been replaced with `mkdocs` and github-pages.
