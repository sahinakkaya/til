If the name or email you are using for your gpg key does not match with the name or email used in git, you may get the following error while trying to sign your commit:
```
error: gpg failed to sign the data
fatal: failed to write commit object
```

To fix this you need to get the your gpg key's id and configure git to use that instead.
```
❯ gpg --list-keys --keyid-format short
/home/sahin/.gnupg/pubring.kbx
------------------------------
pub   rsa4096/CDA15ED2 2022-01-26 [SC] [expires: 2022-02-02]
      XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
uid         [ultimate] Şahin Akkaya (Asocia) <sahin@sahinakkaya.dev>
sub   XXXXXXX/XXXXXXXX 2022-01-26 [E] [expires: 2022-02-02]

❯ git config --global user.signingKey CDA15ED2
```


