# 🧠 Git Learning Journal

## 📁 Day 1: Git Initialization and First Push

### ✅ Terminal History

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
