# FreeIPA

FreeIPA is a comprehensive suite of open source utilities providing an AD like service. 

## User Management

### Add User

### Add Group

### Add User to Group

### Reset User Password

    ipa user-mod john.smith --password

## Host Management

## Misc.

<br>

Retrieve a list of all users in LDAP

    ipa user-find --sizelimit=0 | grep -i "user login" | awk '{print $3}' > ipausers

Retrieve a list of all hosts in LDAP

    ipa host-find --sizelimit=0 | grep -i 'host name' | awk '{print $3}' 

Loop to determine last login dates from user list

    while read i; do
	echo "$i: $(/bin/ipa user-status $i | grep successful)"
    done < ipausers.txt

Search for logins prior to $DATE

    awk '$NF < "20170201"' lastlogins
    
    E.g.

    awk ‘$NF < $(date -d “now -60 days”)