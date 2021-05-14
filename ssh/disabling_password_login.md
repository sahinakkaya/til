You can disable password login by editing `/etc/ssh/sshd_config` like this:
```
File: /etc/ssh/sshd_config
...
ChallengeResponseAuthentication no
PasswordAuthentication no
UsePAM no
```


Before running the following command, **make sure** you have configured ssh keys properly and can login with them. Otherwise you won't be able to login remotely.
```
# you may need to run a different command based on your system
sudo systemctl restart ssh.service
``` 
