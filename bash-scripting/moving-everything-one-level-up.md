You can move every file (except the hidden ones) up by one level in the hierarchy with something like this:
```
for d in */ ; do
    mv $d* .
    rmdir $d # optional
done
```

