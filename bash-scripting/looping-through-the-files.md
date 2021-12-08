You can loop through the files with:
```bash
for f in * ; do
    echo $f
done
```

If you want to loop through only directories:
```bash
for d in */ ; do
    echo $d
done
```
