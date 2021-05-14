If you don't want to type in hostname or username while ssh'ing to a remote servers, you have several options. Let's say you want to run `ssh user@192.168.178.05`. 

- If you are currently logged in as `user` on the current machine, you don't have to specify it. `ssh 192.168.178.05` works.
- If you find it hard to type that address, you can give it an alias. Do this:
```
File: /etc/hosts
...
192.168.178.05 desktop

ssh desktop
# or
ssh user@desktop
```
- If you want to give username **and** host an alias:
```
File: ~/.ssh/config
...
Host myremote             # any name for the host
HostName 192.168.178.05   # IP, .local, or hostname if defined
User username             # your username
Port 22                   # port to listen

ssh myremote
```

