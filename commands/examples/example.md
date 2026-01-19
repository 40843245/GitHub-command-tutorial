# Examples
Available at [GitHub remote repo]()

+ To create a remote repo on GitHub and push it,

first we have to login with GitHub-CLI in terminal.

```
userJay30@ASUS-B1400CBNGW MINGW64 ~ (master)
$ cd "D:\workspace\tutorial projects\GitHub"
```

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub
$ gh auth login
? Where do you use GitHub? GitHub.com
? What is your preferred protocol for Git operations on this host? HTTPS
? Authenticate Git with your GitHub credentials? Yes
? How would you like to authenticate GitHub CLI? Login with a web browser

! First copy your one-time code: A7B8-909C
Press Enter to open https://github.com/login/device in your browser...
✓ Authentication complete.
- gh config set -h github.com git_protocol https
✓ Configured git protocol
✓ Logged in as 40843245
! You were already logged in to this account

```

Then we have to initialize the local repo.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub
$ git init
Initialized empty Git repository in D:/workspace/tutorial projects/GitHub/.git/

```

After that, we can stage it then commit then create and push it at same time (instructions like normal push discussed in Git-tutorial repo)

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub
$ git init
Initialized empty Git repository in D:/workspace/tutorial projects/GitHub/.git/

userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git add .

userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

Add `.gitignore` file to ignore unnecessary file.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ touch .gitignore # 加入忽略檔'.gitignore'
```

Open it with notepad.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ notepad .gitignore
```

Write these in `.gitignore` file.

```
# debug folder
.bin/
.obj/
```

then save it and close it.

After that, stage untracked but changed files.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git add .
```

Ensure that the file is tracked.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   .gitignore
```

Commit the staged file

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git commit -m "Initial commit: add .gitignore"
[master (root-commit) db22c10] Initial commit: add .gitignore
 1 file changed, 3 insertions(+)
 create mode 100644 .gitignore

```

Create an empty remote public repo named `GitHub-example-1` and push the commit atomatically

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ gh repo create GitHub-example-1 --public --source=. --remote=origin --push
✓ Created repository 40843245/GitHub-example-1 on github.com
  https://github.com/40843245/GitHub-example-1
✓ Added remote https://github.com/40843245/GitHub-example-1.git
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 259 bytes | 64.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/40843245/GitHub-example-1.git
 * [new branch]      HEAD -> master
branch 'master' set up to track 'origin/master'.
✓ Pushed commits to https://github.com/40843245/GitHub-example-1.git

```
