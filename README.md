# Useful Terminal commands #

### Search files for specific text using grep ###
* Command
```bash
grep -r 'text' /dir/path/
```
* Example
```bash
grep -r 'foobar' /var/www/App/
grep -r "['id']=" .
```

### Search for file name using find ###
* type is either d for directory or f for file
* name for name and iname to search for name case insensitive
```bash
find /dir/path/ -type d -name "DirName"
find /dir/path/ -type f -iname "FileNameCaseInsensitive"
```
* Example
```bash
find . -type d -iname "*app"
find /var/www/site/ -type d -name "submit"
```

### SSH ###
```bash
# Port is not always needed
ssh -p 1234 uname@ip
```

### SCP ###
* Copy files to/from server
```bash
# Port is not always needed
# Copy local folder to a server
scp -r -P 1234 /local/file/path/ uname@ip:/file/path/
# Copy folder from a server to a local path
scp -r -P 1234 uname@ip:/file/path/ /local/file/path/
```

### View first/last part of a file ###
* View first/last 10 lines of a file
```bash
head file.txt
tail file.txt
```
* Use -f to follow a file and see all changes added to the end
* Example following an error log
```bash
tail -f error.log
```

### Remove ###
* Remove a file
```bash
rm fileName
```
* Remove a folder
```bash
rm -r folderName
# add f option to force remove everything
rm -rf folderName
```

### Make yourself sudo ###
```bash
sudo -s
```

### GIT Commands ###
* Basic commands for pushing to a repository
```bash
git status
git add -A
git commit -m 'message'
git push routeName branchName
```
* [Branches](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
```bash
git checkout -b branchName
```
* Git clean up .git commits 
```bash
git checkout --orphan newBranch
git add -A  # Add all files and commit them
git commit
git branch -D master  # Deletes the master branch
git branch -m master  # Rename the current branch to master
git push -f origin master  # Force push master branch to origin
git gc # Clean up .git folder
```
* Force a 'git pull' and [overwrite local files](http://stackoverflow.com/questions/1125968/how-to-force-git-pull-to-overwrite-local-files)
```bash
git fetch --all
git reset --hard origin/<branch_name>
```

* [Merge branches](http://stackoverflow.com/questions/5601931/best-and-safest-way-to-merge-a-git-branch-into-master)
```bash
git checkout master
git pull origin master # In case master is not up to date
git merge <branch_to_merge>
git push origin master
```

* Working with branches
```bash
# See all branches
git branch
# Creating a new branch
git checkout -b <new_branch_name>
# Re-naming current branch
git branch -m <new_branch_name>
```

* [Delete local/remote branch](http://stackoverflow.com/questions/2003505/how-to-delete-a-git-branch-both-locally-and-remotely)
```bash 
# Delete a local branch
git branch -d <branch_name>
git branch -D <branch_name> # force delete 
# Delete a branch at remote origin
git push origin --delete <branch_name>
```

* Working with remotes
```bash
# View existing remotes
git remote -v
# Delete a remote
git remote remove name
# Change name of a remote
git remote rename old_name new_name
```
