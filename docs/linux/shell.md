# Shell

_All things shell_

## Miscellenous / Glorious one-liners

<br>

Finds anything in current directory that isn't zipped and zips it

    find . -type f ! -iname '*.gz' -exec gzip "{}" \;

Get external IP from CLI

    dig +short myip.opendns.com @resolver1.opendns.com

    curl http://checkip.amazonaws.com/

Move files based on date

    mv `ll | grep 'Jan 31' | awk '{print $9}' [DEST]`

Puppet nuke

    yum -y remove $(rpm -qa | egrep 'puppet|^pe-') ; rm -rf /etc/puppetlabs /opt/puppetlabs /var/log/puppetlabs /etc/sysconfig/p{e-*,uppet}

Print SWAP usage by process

    for file in /proc/*/status; do awk '/VmSwap|Name/{printf $2 " " $3}END{ print ""}' $file; done | sort -k 2 -n -r | less

Test mail CLI

    echo "Subject: E-mail test" | sendmail -v $EMAIL_ADDRESS

Test mail CLI (with attachment)

    echo "Special delivery" | mailx -s "Hello" -a testfile1 $EMAIL_ADDRESS

Shell keepalive

    while true; do echo jh; sleep 30; done