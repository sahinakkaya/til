You can loop through the files with:
```
for f in * ; do
    echo $f
done
```

If you want to loop through only directories:
```
for d in */ ; do
    echo $d
done
```
