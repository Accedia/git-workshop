# Accedia git workshop

## DAY 1, TASK 1:
- clone the repo with 4 simple text files (**estrada.txt**, **himn.txt**, **rap.txt**, **rock.txt**)
- change local user name and email for the specific repo to "Git Workshop <git@workshop.com>"
- make files **new_song.txt** and **aws_credentials.txt**, where **aws_credentials.txt** has sensitive information which shouldn't be committed (add to .gitignore)
- start tracking the new file **new_song.txt** (git add <file>)
- make changes to files **estrada.txt** and **himn.txt** and stage file **himn.txt** along with the new file **new_song.txt**
- commit two of the three changed files (**himn.txt** and **new_song.txt**, file **estrada.txt** stays with changes)

## DAY 1, TASK 2:
- revert the last commit (with --no-commit) and revert only changes to file **himn.txt**
- make changes to file **rap.txt**, stage and commit them along with those to file **estrada.txt** (from previous task)
- make changes to file **rock.txt** and stash them
- add a minor change to file **rap.txt** and amend your last commit
- apply the stash and undo the changes in file **rock.txt** using reset