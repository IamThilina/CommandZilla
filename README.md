##  :penguin: linux
> shows all information about the command
```bash
man command
```
> list all files (including hidden files) with long format (permissions, file sizes, use, group, modification time etc)
```bash
ls -al
```
> print name of current working directory
```bash
pwd
```
> copy files and directories
```bash
cp /src/file dest
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
> change to a specific branch
```git
git checkout task/OE-xxxx-yyyyyyyyyyy
```
> push local change to remote branch
```git
git push origin task/OE-xxxx-yyyyyyyyyyyyy
```
>pull changes from remote branch
```git
git pull origin task/OE-xxx-yyyyyyyyyyyyyy
```
> cancel local commits not pushed to repo
```git
git reset --hard ##########
```
> cancel commits pushed to repo
```git
git revert ###########
```
> see changes made to a file
```git
git diff file
```
> delete a local branch
```git
git branch -D branchName
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

## :snake: python
