Authorized keys for the users stays in the home directory of the user by default. But not every user have home directory. If you want to use your keys to login as a user which does not have home directory, you can do this:

Assuming the name of the user is `git`:
- create `/etc/ssh/authorized_keys_git` and put your key there
- add the following in `/etc/ssh/sshd_config`:
```bash
Match User git
    AuthorizedKeysFile  /etc/ssh/authorized_keys_%u
```
and restart sshd.
