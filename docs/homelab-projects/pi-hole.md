# Pi-hole

Raspberry Pi's are fantastic little pieces of cheap kit. 

One of mine is running `pi-hole` - a network wide ad blocking, DHCP and DNS server. 

It's extremely useful for my homelab providing local dynamic DNS.

Pi-hole remains extremely similar to the DNS/DHCP technology it is built on - DNSMasq - therefore much of the configuration remains the same.

## Install

    curl -sSL https://install.pi-hole.net | bash

_Obligatory piping to bash is bad statement here._

## Configuration

Pi-hole configuration is stored in `/etc/pihole`.

The initial setup configuration is contained within `/etc/pihole/setupVars.conf`.

### Admin console
Pi-hole comes with an admin console with pretty graphs. It's accessable at `http://$MYHOSTNAME/admin`.

#### Modify or remove admin password

With console access, either local or SSH, run:

    pihole -a -p

Leave blank for no password on the admin portal. 

### DHCP
DHCP is disabled by default but can be turned on and configured via the admin portal. 

The configuration is stored in `/etc/dnsmasq.d/`.

Active DHCP leases are stored in `/etc/dnsmasq.d/02-pihole-dhcp.conf` and **static** IP addresses are configured in `04-pihole-static-dhcp.conf`.

### DNS

### Ad-Blocking
