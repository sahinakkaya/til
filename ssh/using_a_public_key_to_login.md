You can generate authentication keys and use it with ssh to login. First run the below command if you don't have any (it won't overwrite if you already have one):

```bash
ssh-keygen
```

Then copy your public key to remote server with this:
```bash
ssh-copy-id name@host
```

From now on, you should be able to login with `ssh name@host` without having to enter your password.

