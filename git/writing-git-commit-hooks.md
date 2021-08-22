Since the commit messages of this repository is always goes like `TIL: Name of the added file without dashes` I thought I can automate this. First I wrote a macro inside neovim and save it in my `init.lua`. But hey, there is a better tool for this: [git hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks). After reading the docs, I wrote the following script and put it inside `.git/hooks/prepare-commit-msg`:

```bash
#!/bin/bash

COMMIT_MSG_FILE=$1
COMMIT_SOURCE=$2
SHA1=$3
 
# Only add custom message when there is no commit source
# ($COMMIT_SOURCE is empty). Otherwise, keep the default message
# proposed by Git. Possible commit source: message, template,
# merge, squash or commit. See https://git-scm.com/docs/githooks
if [[ -z "$COMMIT_SOURCE" ]]
then
  hint=$(cat "$COMMIT_MSG_FILE")
  message=$(git diff --cached --name-status -r | cut -d/ -f2 | sed 's/-/ /g' | cut -d. -f1 | sed 's/.*/\u&/') 
  echo "TIL: ${message}" > $COMMIT_MSG_FILE
  echo "$hint" >> "$COMMIT_MSG_FILE"
fi
```

And that's all. I never need to enter a commit message for this repository from now on.
