You can use `touch` to change modification date or time of a file:
```bash
touch -d 20210703 filename

# Set the times on a file to a specific date and time:
touch -t YYYYMMDDHHMM.SS filename
```


... or use the times from a file to set the times on a second file:

```bash
touch -r filename filename2
```
