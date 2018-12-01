# Accedia git workshop

## Commands reference.
```
git clone <repository-address>
git config --local user.name <user-name>
git config --local user.email <email>
git add .gitignore
git commit -m "Add aws_credentials to the gitignore"
git add <filename>
git add <filename>
git commit -m <commit-message>
```

```
git revert --no-commit <commit-hash>
git reset HEAD <filename>
git revert --continue
git add <filename>
git add <filename>
git commit -m <commit-message>
git add <filename>
git stash save <stash-message>
git stash pop
git stash add <filename>
git commit --amend
git reset --soft <commit-hash>
```

## DAY 1, TASK 1:
- Clone the **accedia-git-workshop** repository locally.
- Change the local user name for that specific repository to "Git Worksop". :scroll:  Tip: Do not forget to include the --local option.
- Change the local email address for that specific repo to "git@workshop.com". Again, do not forget to include the --local option.
- Create new blank text file in the directory of the cloned repo, name it **new_song.txt**.<br />
- Create second text file and name it **aws_credentials.txt**. This file is going to contain sensitive information - please use the text below for the file content.
```
[default]
aws_access_key_id=AKIAIOSFODNN7EXAMPLE
aws_secret_access_key=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
``` 
  The git status should show the newly created files as the screen below:
  ![Task expected result](https://raw.githubusercontent.com/Jessie365/accedia-git-workshop/images/images/task1-1.jpg)
- Add **aws_credentials.txt** to the .gitignore. This is done by opening the file **.gitignore** and adding new line with the file name that we want to be ignored. Save and close the file.<br />:scroll: Tip: Include the file extension when adding the file to the .gitignore.
- Commit the changes made to the **.gitignore** file by staging the file and then issuing the commit command. Please name your commit "Add aws_credentials to the gitignore".
  <br />
  Your status should look like that:
 ![Task expected result](https://raw.githubusercontent.com/Jessie365/accedia-git-workshop/images/images/task1-2.jpg)
- Open file **estrada.txt** and duplicate the last line. Save and close the file.
- Open file **himn.txt** and duplicate the last line. Save and close the file.
- Stage files **himn.txt** and **new_song.txt** by issuing git add command twice.
  Your status should look like that:
  ![Task expected result](https://raw.githubusercontent.com/Jessie365/accedia-git-workshop/images/images/task1-3.jpg)
- Commit the changes with the following message "Add new song"
  Your log should look like the screen below. Notice the author of the commits.
  ![Task expected result](https://raw.githubusercontent.com/Jessie365/accedia-git-workshop/images/images/task1-4.jpg)

## DAY 1, TASK 2:
- Let’s imagine that the changes made by the last commit on file **himn.txt** were made by accident and we need to revert them, but keep the **new_song.txt**.
This can be done with the ```git revert``` command, using the --no-commit option and passing the commit hash of the last commit.<br />
Once you execute the ```git revert``` command, your log should look like the screen below.
Notice that the reverted changes are now staged and if we proceed with the revert, we are going to revert both changes but we do NOT want that.
  ![Task expected result](https://raw.githubusercontent.com/Jessie365/accedia-git-workshop/images/images/task2-1.jpg)
- Unstage the changes for **new_song.txt** by executing ```git reset HEAD <filename>``` command. <br />:scroll: Tip: Read the description that was displayed after executing the revert command. It is very descriptive, and you can find that one of the proposals is to execute the described command.
  After unstaging the file, your status should look like that:
  ![Task expected result](https://raw.githubusercontent.com/Jessie365/accedia-git-workshop/images/images/task2-2.jpg)
- Continue with the revert by executing ```git revert``` command with option --continue. The default editor should pop up giving a default name of the new commit (Revert "Add new song"), please change the name to "Revert himn.txt file only".
  Once we are done with the revert the log should look like that:
  ![Task expected result](https://raw.githubusercontent.com/Jessie365/accedia-git-workshop/images/images/task2-3.jpg)
- Open **rap.txt** and duplicate the last line. Save and close the file. Stage the changes made on **rap.txt** and **estrada.txt** and commit them, please name your commit "Change rap and estrada songs".<br />:scroll: Tip: You can stage both files by executing ```git add``` and putting the two filenames separated with whitespace.
- Let’s experiment with the stash that git provides for us. Open **rock.txt** file and make some random changes. Save and close the file. Stage the changes made on **rock.txt** and stash them.<br />:scroll: Tip: You can include a message for the stashed changes by using ```git stash save "name"```. Try entering "Update rock.txt file" for the stash message.
  Executing the ```git stash list``` command should show the following:
  ![Task expected result](https://raw.githubusercontent.com/Jessie365/accedia-git-workshop/images/images/task2-4.jpg)
- Apply the stash by executing the ```git stash pop``` command. This will apply the stashed changes and remove the item from your stash. You can confirm that the item is removed by listing the stash again.
- Now we would like to include the changes from **rock.txt**, that were pulled from our stash, to our last commit. This can be easily achieved by executing the ```git commit``` command with the --amend option. Do not forget to stage **rock.txt** before proceeding with the amend.
 After executing the command, your default editor should pop up, please change the commit message to "Add rock file". Save and close.
Your log should look like that:
  ![Task expected result](https://raw.githubusercontent.com/Jessie365/accedia-git-workshop/images/images/task2-5.jpg)
- The last thing that we are going to try is to reset the last commit, but keeping the changes as staged. This can be done by executing ```git reset``` command with the --soft option.<br />:scroll:  Tip: Instead of providing the commit hash, you can use HEAD~1 as a reference to the second commit in your log.
Your log after resetting the commit should look like that:
   ![Task expected result](https://raw.githubusercontent.com/Jessie365/accedia-git-workshop/images/images/task2-6.jpg)
Your status should look like the screen below. Notice that the changes of the commit, that we reset, are staged.
  ![Task expected result](https://raw.githubusercontent.com/Jessie365/accedia-git-workshop/images/images/task2-7.jpg)
