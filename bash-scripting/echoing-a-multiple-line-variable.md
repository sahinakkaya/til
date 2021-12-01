If you are wondering why `echo` doesn't print the output on multiple lines, make sure there is `"` around your variable. 

> The difference is that the double-quoted version of the variable (echo "$RESULT") preserves internal spacing of the value exactly as it is represented in the variable — newlines, tabs, multiple blanks and all — whereas the unquoted version (echo $RESULT) replaces each sequence of one or more blanks, tabs and newlines with a single space. 
