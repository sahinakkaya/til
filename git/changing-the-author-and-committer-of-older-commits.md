You can change author of your commits to anyone. Let's make all the commit's of the current repository Torvalds :D Luckily we know his email address so this will be very easy. Just run:
```
git filter-branch --env-filter '
OLD_EMAIL="akkayas17@itu.edu.tr"
CORRECT_NAME="Linus Torvals"
CORRECT_EMAIL="torvalds@linux-foundation.org"
if [ "$GIT_COMMITTER_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_COMMITTER_NAME="$CORRECT_NAME"
    export GIT_COMMITTER_EMAIL="$CORRECT_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_AUTHOR_NAME="$CORRECT_NAME"
    export GIT_AUTHOR_EMAIL="$CORRECT_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags
```

and we are done! :D

![Linus Torvalds is here](https://raw.github.com/Asocia/til/master/img/linus.jpg)
