You can split a string with `cut`:

```
foo="hello-world-bye-world"
bar=$(echo $foo | cut -d"-" -f2)
echo $bar
# world 
```
