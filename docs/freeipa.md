# FreeIPA

FreeIPA is a comprehensive suite of open source utilities providing an AD like service. 

## User Management

Add User

Add Group

Add User to Group

Reset User Password

```bash
ipa user-mod john.smith --password
```

<br>

## Host Management

## Misc.

<br>

Retrieve a list of all users in LDAP

```bash
ipa user-find --sizelimit=0 | grep -i "user login" | awk '{print $3}' > ipausers
```

<br>

Retrieve a list of all hosts in LDAP

```bash
ipa host-find --sizelimit=0 | grep -i 'host name' | awk '{print $3}' 
```

<br>

Loop to determine last login dates from user list

```bash
while read i; do
  echo "$i: $(/bin/ipa user-status $i | grep successful)"
done < ipausers.txt
```

<br>

Search for logins prior to $DATE

```bash
awk '$NF < "20170201"' lastlogins
```
    E.g.

```bash
awk ‘$NF < $(date -d “now -60 days”)
```