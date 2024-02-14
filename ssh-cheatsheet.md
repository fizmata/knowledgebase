### Port forwarding
You can forward a local port (e.g 8080) which you can then use to access the application locally as follows. The -L flag defines the port forwarded to the remote host and remote port.

```
$ ssh admin@server1.example.com -L 8080:server1.example.com:3000
```
Adding the -N flag means do not execute a remote command, you will not get a shell in this case.
```
$ ssh -N admin@server1.example.com -L 8080:server1.example.com:3000
```
The -f switch instructs ssh to run in the background.
```
$ ssh -f -N admin@server1.example.com -L 8080:server1.example.com:3000
```

### To get key to remote machine 
```
ssh-copy-id
```


### when ssh hangs
try to exit the SSH session by typing `~.`

