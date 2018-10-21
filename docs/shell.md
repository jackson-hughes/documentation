# Shell

_All things shell_

## Miscellenous / Glorious one-liners

<br>

Finds anything in current directory that isn't zipped and zips it

```bash
find . -type f ! -iname '*.gz' -exec gzip "{}" \;
```

<br>

Get external IP from CLI

```bash tab="Curl"
curl http://checkip.amazonaws.com/
```

```bash tab="DNS"
dig +short myip.opendns.com @resolver1.opendns.com
```

<br>

Move files based on date

```bash
mv `ll | grep 'Jan 31' | awk '{print $9}' [DEST]`
```

<br>

Puppet nuke

```bash
yum -y remove $(rpm -qa | egrep 'puppet|^pe-') ; rm -rf /etc/puppetlabs /opt/puppetlabs /var/log/puppetlabs /etc/sysconfig/p{e-*,uppet}
```

<br>

Print SWAP usage by process

```bash
for file in /proc/*/status; do awk '/VmSwap|Name/{printf $2 " " $3}END{ print ""}' $file; done | sort -k 2 -n -r | less
```

<br>

Test mail CLI

```bash tab="Sendmail"
echo "Subject: E-mail test" | sendmail -v $EMAIL_ADDRESS
```

```bash tab="Mailx (attachment)"
echo "Special delivery" | mailx -s "Hello" -a testfile1 $EMAIL_ADDRESS
```

<br>

Shell keepalive

```bash
while true; do echo jh; sleep 30; done
```
