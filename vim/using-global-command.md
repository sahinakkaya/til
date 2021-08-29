The global command `:g[lobal]` is very powerful. It is used to execute a command matching a pattern. The syntax is 

```
:[range]g/pattern/cmd
```

The default range is whole file. If you want to change the range here is a reference table for substitution.

| Range  | Description                           | Example             |
| ------ | --------------------------------------| --------------------|
| 28     | line 28                               | :28s/bad/good/g     |
| 1      | first line                            | :1s/bad/good/g      |
| $      | last line                             | :$s/bad/good/g      |
| %      | all lines in a file (same as 1,$)     | :%s/bad/good/g      |
| 6,28   | lines 6 to 28 inclusive               | :6,28s/bad/good/g   |
| 11,$   | lines 11 to end of the file           | :11,$s/bad/good/g   |
| .,$    | current line to end of the file       | :.,$s/bad/good/g    |
| .+1,$  | line after current line to end        | :.+1,$s/bad/good/g  |
| .,+4   | current to current+5 line, inclusive) | :.,.+4s/bad/good/g  |
| ?a?,/b | between patterns a and b, inclusive)  | :?a?,/b/s/bad/good  |


Example global commands:

 - `:g/error/d` - delete all lines containing string `error`
 - `g!/important/d` - delete all lines **not** containing string `important`
 - `4,10t15` - copy all lines between 4 and 10 **t**o line 15
 - `4,10m15` - **m**ove all lines between 4 and 10 **t**o line 15
 - `:5,18g/^foo/normal 0df=` - run normal command `0df=` on the lines between 5 and 18 which starts with string `foo`


