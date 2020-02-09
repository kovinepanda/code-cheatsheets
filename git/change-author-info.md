
# Changing author info

Copy and paste the script, replacing the following variables based on the information you gathered:

    OLD_EMAIL
    CORRECT_NAME
    CORRECT_EMAIL

```bash
#!/bin/sh

git filter-branch --env-filter '

OLD_EMAIL="your-old-email@example.com"
CORRECT_NAME="Mindaugas Urbontaitis"
CORRECT_EMAIL="your-correc-email@example.com"

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

> Source:
> [https://help.github.com/en/github/using-git/changing-author-info](https://help.github.com/en/github/using-git/changing-author-info)