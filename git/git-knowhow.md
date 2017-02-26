
Change the author and committer name and e-mail of multiple commits in Git

ref : [stackoverflow](http://stackoverflow.com/questions/750172/change-the-author-and-committer-name-and-e-mail-of-multiple-commits-in-git)

```sh
#!/bin/sh

git filter-branch --env-filter '
OLD_EMAIL="your-old-email@example.com"
CORRECT_NAME="Your Correct Name"
CORRECT_EMAIL="your-correct-email@example.com"
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


Changing a remote's URL

ref : [link](https://help.github.com/articles/changing-a-remote-s-url/)

```sh
git remote set-url origin https://github.com/USERNAME/OTHERREPOSITORY.git
```

Git show config

```
$ git config --list
```
