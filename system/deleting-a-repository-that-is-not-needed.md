Say you added a repository with `sudo add-apt-repository -y ppa:...` and you want to delete it maybe because it gives you an error while you are trying to update your system:
```
E: The repository 'http://ppa.launchpad.net/...' does not have a Release file.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
```

You will need to find corresponding file in `sources.list.d` and delete it.

```
cd /etc/apt/sources.list.d
sudo rm bad-repo.list
```
