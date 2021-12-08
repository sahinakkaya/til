1. Redirect stdout to one file and stderr to another file:
```bash
command > out 2>error
```
2. Redirect stdout to a file `out`, and then redirect stderr to stdout:
```bash
command > out 2>&1
```
