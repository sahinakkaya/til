Today I got this error:
```
Bad owner or permissions on /home/sahin/.ssh/config
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```
As you might guess, I have already checked the ownership of the related files and everything looked normal:

```
❯ ls -la
drwx------ sahin sahin 4.0 KB Sat Oct 30 19:52:11 2021  .
drwxr-xr-x sahin sahin  12 KB Sat Oct 30 20:04:50 2021  ..
.rw-rw-r-- sahin sahin 393 B  Mon May 10 18:56:48 2021  authorized_keys
.rw-r--r-- sahin sahin  83 B  Sun May 16 14:59:48 2021  config
.rw------- sahin sahin 1.6 KB Fri Nov  9 19:15:12 2018  id_rsa
.rw-r--r-- sahin sahin 393 B  Mon May 10 20:53:33 2021  id_rsa.pub
.rw-r--r-- sahin sahin 7.6 KB Mon Aug 16 18:07:27 2021  known_hosts
```
But I missed something. The permissions of the `~/.ssh/config` file needs to be `600` but it was `644`. After changing it, the problem is gone.
```
❯ stat -c %a config
644
❯ chmod 600 config
```
