You can get the size of a file in bytes with:
```bash
stat -c %s file_name
# example
size=$(stat -c %s $myfile)
```
