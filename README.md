##  :penguin: Linux



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
