##  :penguin: linux
> shows all information about the command
```bash
man command
```
> list all files (including hidden files) with long format (permissions, file sizes, user, group, modification time etc)
```bash
ls -al
```
> print name of current working directory
```bash
pwd
```
> copy file
```bash
cp /src/file dest
```
> copy directory
```bash
cp -r /src/dir dest
```
> move file
```bash
mv src/file dest/
```
> move a directory
```bash
mv -t dest/ src/dir
```
> rename a file or directory
```bash
mv src/oldfile src/newfile
mv src/oldDir src/newDir
```
> remove files or directories 
```bash
rm src/file
rm -rf src/dir
```
> prints recently used commands
```bash
history
```
> concatenate files and print on the standard output
```bash
cat file1 file2
cat -n file1
```
> print lines matching a pattern
```bash
grep pattern file
```
> print the number of newlines, words, and bytes in a file
```bash
wc file
```
> sort lines of text files
```bash
sort file
```
> list all user
```bash
cat /etc/passwd
```
#### Linux File Permissions

* 3 types of file permissions - **read, write, execute**
* 10 bit format
```text
        1        2 3 4     5 6 7    8 9 10
    file type    owner     group    others
```
>**eg.** drwxrw-­r­­--   means owner has all three permissions, group has read and write, others have only read permission

* read permission – 4, write – 2, execute ­1 
> **eg.**  rwxrw­r­­ = 764


> change file access permissions
```bash
chmod mode file
```
> change file owner and group 
```bash
chown owner-user file
chown owner-user:owner-group file
chown owner-user:owner-group directory
```
#### System Administration
> switch user
```bash
su user
```
> update  a user’s authentication
```bash
passwd
```
> show who is logged on
```bash
who
```
> remove a user
```bash
userdel username
```
#### Process Management
> snapshot of the current processes
```bash
ps
```
> kill a process(using signal mechanism) 
```bash
kill -9 pid
```
#### Archival
> archive a file
```bash
tar -xvzf dest/ src/file.tar
```
> package and compress (archive) files
```bash
zip dest/dir.zip src/dir
```
> extract compressed files in a ZIP archive
```bash
unzip src/dir.zip -d dest/
```

## ssh
> connect to a remote server with ssh
```ssh
ssh -i path/key user@host
```
> keep ssh connection live
```ssh
ssh -o TCPKeepAlive=yes user@host
```
>generate ssh key pair
```ssh
ssh-keygen
```
> copy public key to remotehost
```ssh
ssh-copy-id -i ~/.ssh/mykey user@host
```
> copy to remote host
```ssh
scp /source/file user@remotehost:/dest/
```
> copy from remote host
```ssh
scp user@remotehost:/source/file /dest/
```
> remote port forwarding
```ssh
ssh -R remotePort:localhost:localPort user@host
```
> local port forwarding
```ssh
ssh -L localPort:localhost:remotePort user@host
```

## :octocat: git

> clone a specific branch
```git
git clone -b branch-name repo-url
```
> create and checkout to a new branch
```git
git checkout -b [branch-name]
```
> checkout to a specific branch
```git
git checkout [branch-name]
```
> checkout to a specific commit
```git
git checkout [commit-checksum]
```
> push local change to remote branch
```git
git push [remote-name] [branch-name]
```
>pull changes from remote branch
```git
git pull [remote-name] [branch-name]
```
> cancel local commits not pushed to repo
```git
git reset --hard [commit-checksum]
```
> cancel commits pushed to repo
```git
git revert [commit-checksum]
```
> see changes made to a file
```git
git diff <file>
```
> delete a local branch
```git
git branch -D [branch-name]
```
> fetch latest branches
```git
git fetch
```
> remove a file from Git (you have to remove it from your tracked files, more accurately, remove it from your staging area and then commit)
```git
git rm <file>
```
> remove a file from staging area but keep it in working tree
```git
git rm --cashed <file>
```
> print all commits in a single line
```git
git log --pretty=oneline
```
> override previous commit if its not pushed ( you commit too early and possibly forget to add some files, or you mess up your commit message. do the forgotten work and run the following command)
```git
git commit --amend
```
> unstaging a staged File
```git
git reset HEAD <file>
```
> unmodifying a modified File
```git
git checkout -- <file>
```
> list remotes with urls
```git
git remote -v
```
> adding remote repositories
```git
git remote add <shortname> <url>
```
> renaming remote repositories
```git
git remote rename <old-name> <new-name>
```
> show more information about remote repos (branching information)
```git
git remote show [remote-name]
```
> Git has the ability to tag specific points in history as being important. Typically people use this functionality to mark release points
> Git uses two main types of tags: lightweight and annotated.
>A lightweight tag is very much like a branch that doesn’t change – it’s just a pointer to a specific commit.
>Annotated tags, however, are stored as full objects in the Git database. They’re checksummed; contain the tagger name, email, and date; have a tagging message; and can be signed and verified with GNU Privacy Guard (GPG). It’s generally recommended that you create annotated tags so you can have all this information; but if you want a temporary tag or for some reason don’t want to keep the other information, lightweight tags are available too.
> list all tags
```git
git tag
```
> search for tags with a particular pattern
```git
git tag -l "v1.8.5*"
```
> creating an annotated tag
```git
git tag -a [tag] -m [tag-message]
```
> see the tag data along with the commit
```git
git show [tag]
```
> tag commits after you’ve moved past them
```git
git tag -a [tag] [commit-checksum]
```
> By default, the git push command doesn’t transfer tags to remote servers. You will have to explicitly push tags to a shared server after you have created them. This process is just like sharing remote branches
```git
git push [remote-name] [tagname]
```
> You can’t really check out a tag in Git, since they can’t be moved around. If you want to put a version of your repository in your working directory that looks like a specific tag, you can create a new branch at a specific tag with
```git
git checkout -b [branchname] [tagname]
```
>  push dirty working tree state onto your stack
```git
git stash
```
>  see which stashes you’ve stored
```git
git stash list
```
>  re apply stashes you’ve stored
```git
git stash apply stash@{[stash-number]}
```
>  push to another branch
```git
git push [remote-name] [branch-1]:[branch-2]
```
>  change configuration to avoid typing password every time you push
```git
git config remote.origin.url https://{USERNAME}:{PASSWORD}@github.com/{USERNAME}/{REPONAME}.git
```
>  Edit pushed commit messages
```git
git rebase -i HEAD~n
```
Replace pick with reword before each commit message you want to change.
Save and close the commit list file.
In each resulting commit file, type the new commit message, save the file, and close it.
```git
git push --force
```
## :dolphin: mysql

> login
```mysql
mysql -u user -p
```
> get mysql dump
```mysql
mysqldump -u user -p dbname > db.sql
```
> restore mysql backup
```mysql
mysql -u user -p dbname < db.sql
```

## node

> run js file
```node
node file.js
```
> run npm scripts
```npm
npm run scriptName
```
> install dependencies in package.json
```npm
npm install
```
> install dependencies except devDependencies
```npm
npm install --production
```
> install packages globally
```npm
npm install package -g
```
> install and save packages to package.json
```npm
npm install package --save
```
> install and save devDependencies to package.json
```npm
npm install package --save-dev
```
> install and save optionalDependencies to package.json
```npm
npm install package --save-optional
```
> update all the packages listed to the latest version
```npm
npm update
```
> update globally installed packages
```npm
npm update -g
```
> update a package and save the new version as the minimum required dependency in package.json
```npm
npm update --save
```
> see if any installed packages are currently outdated
```npm
npm outdated
```
>  print all the versions of packages that are installed, as well as their dependencies, in a tree-structure
```npm
npm ls
```
> install a specific node version
```nvm
nvm install version
```
> switch to a specific node version
```nvm
nvm use version
```
> ENOSPC error
```bash
echo fs.inotify.max_user_watches=582222 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```

## :snake: python
