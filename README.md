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
