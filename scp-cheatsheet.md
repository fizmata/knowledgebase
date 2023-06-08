
SCP (Secure Copy) Command Cheatsheet

1. Copy a local file to a remote server:
```
scp /path/to/local/file.txt username@remote:/path/on/remote/
```

2. Copy a remote file to a local directory:
```
scp username@remote:/path/to/remote/file.txt /path/on/local/
```

3. Copy a directory from the local system to a remote server:
```
scp -r /path/to/local/directory/ username@remote:/path/on/remote/
```

4. Copy a directory from a remote server to the local system:
```
scp -r username@remote:/path/to/remote/directory/ /path/on/local/
```

5. Copy multiple files from the local system to a remote server:
```
scp file1.txt file2.txt username@remote:/path/on/remote/
```

6. Copy multiple files from a remote server to the local system:
```
scp username@remote:/path/to/remote/file1.txt username@remote:/path/to/remote/file2.txt /path/on/local/
```

7. Copy a file using a specific port (e.g., port 2222):
```
scp -P 2222 /path/to/local/file.txt username@remote:/path/on/remote/
```

8. Copy files while preserving the file attributes and timestamps:
```
scp -p /path/to/local/file.txt username@remote:/path/on/remote/
```

9. Copy files in verbose mode to see detailed progress and debugging information:
```
scp -v /path/to/local/file.txt username@remote:/path/on/remote/
```

10. Copy files using a specific SSH private key file:
```
scp -i /path/to/private_key.pem /path/to/local/file.txt username@remote:/path/on/remote/
```

Remember to replace `/path/to/local` with the actual local file or directory path, `username` with your remote server username, `remote` with the remote server's address, and `/path/on/remote` with the destination path on the remote server.

Please note that SCP uses SSH for secure file transfers and requires SSH access to the remote server.
