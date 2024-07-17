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
---------------------------------
### To get key to remote machine 
```
ssh-copy-id
```

------------------------------------
### ssh escape character

```
Supported escape sequences:
 ~.   - terminate connection (and any multiplexed sessions)
 ~B   - send a BREAK to the remote system
 ~C   - open a command line
 ~R   - request rekey
 ~V/v - decrease/increase verbosity (LogLevel)
 ~^Z  - suspend ssh
 ~#   - list forwarded connections
 ~&   - background ssh (when waiting for connections to terminate)
 ~?   - this message
 ~~   - send the escape character by typing it twice
(Note that escapes are only recognized immediately after newline.)
```


https://linuxize.com/post/using-the-ssh-config-file/
