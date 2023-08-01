### File Permissions 

Folders should always get execution permission, otherwise they can not be opened. If files inside get `0640` folder should be `0750`.

## SYSTEMD

### Search for Service
```
systemctl --type=service | grep <service-name>
```

## Enviromnental Variables

`/etc/environment` is the place to set variables for every user

## To ship stuff
self-extractable archives on Unix - https://makeself.io/

to extract makeself archive without running it:
```
<archive.sh> --noexec --target /tmp/destination
```
