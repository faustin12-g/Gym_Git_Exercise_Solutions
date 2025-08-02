# Git Learning Journal

## Day 1: Git Initialization and First Push

### Terminal History

#### 1. i. Exercise 1 Bundle 1

```powershell
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git init
Initialized empty Git repository in C:/Users/USER/Desktop/Overall/THE GYM/GIT/.git/

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
        file.html

nothing added to commit but untracked files present (use "git add" to track)

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git add .

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git commit -m "First commit"
[master (root-commit) 6ed3fdd] First commit
 2 files changed, 18 insertions(+)
 create mode 100644 README.md
 create mode 100644 file.html

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git remote add origin https://github.com/faustin12-g/git_ninja.git

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git branch
* master

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git branch -m master main

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git branch
* main

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git push origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 12 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 513 bytes | 513.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/faustin12-g/git_ninja.git
 * [new branch]      main -> main
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git checkout -b dev
Switched to a new branch 'dev'
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git branch test
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git branch -a
* dev
  main
  test
  remotes/origin/main
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git branch -d test
Deleted branch test (was d0ef8f1).
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git branch
* dev
  main 
```

#### Bundle 1 exercise 2

```
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash save "home changes"
Saved working directory and index state On main: home changes
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash save "about changes"
No local changes to save
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git add about.html
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash save "about changes"
Saved working directory and index state On main: about changes
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git add team.html
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash save "team page changes"
Saved working directory and index state On main: team page changes
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash list
stash@{0}: On main: team page changes
stash@{1}: On main: about changes
stash@{2}: On main: home changes

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash pop stash@{1}
error: unknown switch `e'
usage: git stash pop [--index] [-q | --quiet] [<stash>]

    -q, --[no-]quiet      be quiet, only report errors
    --[no-]index          attempt to recreate the index

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash pop "stash@{1}"
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Dropped stash@{1} (cf6dcd9f228c6f1f06dcca79b3381fb26f852824)
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash pop "stash@{2}"
Already up to date.
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        team.html

Dropped stash@{2} (8454fe4c592d0a384fbacb356b5dd52430e2ffc4)
 GYM\GIT> git stash list         
stash@{0}: On main: team page changes
stash@{1}: On main: home changes
stash@{2}: WIP on main: 6341905 update 
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash pop "stash@{2}"
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   home.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        team.html

Dropped stash@{2} (5cb84004b29081c0cc06b6a78404fceec38f2de1)
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   home.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        team.html

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git commit -m "Home and about pages changes"
[main 06b64b5] Home and about pages changes
 1 file changed, 11 insertions(+)
 create mode 100644 home.html
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git push origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 292 bytes | 292.00 KiB/s, done.
Total 2 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/faustin12-g/Gym_Git_Exercise_Solutions
   6341905..06b64b5  main -> main
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash list         
stash@{0}: On main: team changes
stash@{1}: On main: team page changes
stash@{2}: WIP on main: 6341905 update README.md file
stash@{3}: WIP on main: 6341905 update README.md file
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash pop "stash@{0}"
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        team.html

Dropped stash@{0} (36aadc56d75ffcf92a588d1913187210d7dd05d0)
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        team.html

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git commit -m "About added"
[main c743076] About added
 1 file changed, 11 insertions(+)
 create mode 100644 about.html
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git push origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 234 bytes | 234.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/faustin12-g/Gym_Git_Exercise_Solutions
   06b64b5..c743076  main -> main
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        team.html

nothing added to commit but untracked files present (use "git add" to track)
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash pop "stash@{0}"
error: The following untracked working tree files would be overwritten by merge:
        team.html
Please move or remove them before you merge.
Aborting
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        team.html

nothing added to commit but untracked files present (use "git add" to track)
The stash entry is kept in case you need it again.
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git add team.html
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git restore team.html
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git reset --soft HEAD~1
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html
        new file:   team.html

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git reset --soft HEAD~1
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html
        new file:   home.html
        new file:   team.html

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git restore team.html
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html
        new file:   home.html
        new file:   team.html

PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash save "team"
Saved working directory and index state On main: team
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash list
stash@{0}: On main: team
stash@{1}: On main: team page changes
stash@{2}: WIP on main: 6341905 update README.md file
stash@{3}: WIP on main: 6341905 update README.md file
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash pop "stash@{0}"
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html
        new file:   home.html
        new file:   team.html

Dropped stash@{0} (6baf20e65f17584d0fc4e01ea03b4c442e2efb05)
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash list
stash@{0}: On main: team page changes
stash@{1}: WIP on main: 6341905 update README.md file
stash@{2}: WIP on main: 6341905 update README.md file
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git stash pop "stash@{0}"
Auto-merging team.html
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html
        new file:   home.html
        new file:   team.html

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   team.html

Dropped stash@{0} (dba89c8dbacb018731245bd68fb1d866ed3b82ae)
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git restore team.html
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> 
```


#### 2. Bundle 2 exercise 1
```
PS C:\Users\USER\Desktop\Overall\THE GYM\GIT> git checkout -b ft/bundle-2
Switched to a new branch 'ft/bundle-2'

Create services.html manually

