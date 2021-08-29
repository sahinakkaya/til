1. Redirect stdout to one file and stderr to another file:

    command > out 2>error

2. Redirect stdout to a file `out`, and then redirect stderr to stdout:

    command > out 2>&1

