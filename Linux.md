## File Permissions 

Folders should always get execution permission, otherwise they can not be opened. If files inside get `0640` folder should be `0750`.

## grep

one does not need to `cat` to grep:
```
grep [expression] [file]
```

you can grep whole dirs too usring `-r` flag.

igrone case:
```
grep -i
```

use multiple expressions
```
grep -e [exp1] -e [exp2]
```

count mathes:
```
grep -c
```

to follow stuff like `tail -f` follow it with a pipe line and:
```
grep --line-buffered [exp]
```

## SYSTEMD



### Search for Service
```
systemctl --type=service | grep <service-name>
```

### Under what user service runs
```
systemctl show -pUser,UID nginx
```
If User shows nothing, and UID is [not set], the service is running as root, or the owning user in the case of a user service.

## Enviromnental Variables


`/etc/environment` is the place to set variables for every user

## To ship stuff
self-extractable archives on Unix - https://makeself.io/

to extract makeself archive without running it:
```
<archive.sh> --noexec --target /tmp/destination
```

## apt

to list all available version of the package:
```
apt-cache show
```

## Linux Networking

### Network manage TUI

`nmtui` is a text based user interface, usefull for changeing IPs, Netmasks, etc.

### Firewalld

To open a port:
```
firewall-cmd --permanent --zone=public --add-port=80/tcp
```
and then to apply:
```
firewall-cmd --reload
```
show applied rules
```
firewall-cmd --list-all-zones
```

In case you need none permament opening just remove `--permanent` flag from the first command. That way rules will reset after reboot.

## Processes 

for tree view of all processes use `--forest` flag
```
ps -auxf
```
