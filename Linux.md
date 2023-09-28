### File Permissions 

Folders should always get execution permission, otherwise they can not be opened. If files inside get `0640` folder should be `0750`.

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
