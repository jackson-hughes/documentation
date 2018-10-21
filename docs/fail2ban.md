# Fail2ban

## Installation

To-do

## Managing jails

List all currently blocked IP addresses in all jails

```bash
fail2ban-client status | grep "Jail list:" | sed "s/ //g" | awk '{split($2,a,",");for(i in a) system("fail2ban-client status " a[i])}' | grep "Status\|IP list"
```

<br>

Unban an IP address

```bash
fail2ban-client set $JAIL_NAME unbanip 1.2.3.4
```
