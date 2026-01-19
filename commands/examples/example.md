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

Let's get started to write first `C#` script.

+ First, we need to create a directory then create a console project under the directory.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ mkdir "MyAwesomeApp"

userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ cd "MyAwesomeApp"

userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub/MyAwesomeApp (master)
$ dotnet new console
The template "Console App" was created successfully.

Processing post-creation actions...
Restoring D:\workspace\tutorial projects\GitHub\MyAwesomeApp\MyAwesomeApp.csproj:
Restore succeeded.

```

Change back to root directory of local repo.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub/MyAwesomeApp (master)
$ cd ..
```

+ To push the empty project,

we have to stage them.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git add .
```

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   MyAwesomeApp/MyAwesomeApp.csproj
        new file:   MyAwesomeApp/Program.cs
        new file:   MyAwesomeApp/obj/MyAwesomeApp.csproj.nuget.dgspec.json
        new file:   MyAwesomeApp/obj/MyAwesomeApp.csproj.nuget.g.props
        new file:   MyAwesomeApp/obj/MyAwesomeApp.csproj.nuget.g.targets
        new file:   MyAwesomeApp/obj/project.assets.json
        new file:   MyAwesomeApp/obj/project.nuget.cache
```

Then commit it 

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git commit -m "Part 0: Create a new empty console project"
[master 567a803] Part 0: Create a new empty console project
 7 files changed, 740 insertions(+)
 create mode 100644 MyAwesomeApp/MyAwesomeApp.csproj
 create mode 100644 MyAwesomeApp/Program.cs
 create mode 100644 MyAwesomeApp/obj/MyAwesomeApp.csproj.nuget.dgspec.json
 create mode 100644 MyAwesomeApp/obj/MyAwesomeApp.csproj.nuget.g.props
 create mode 100644 MyAwesomeApp/obj/MyAwesomeApp.csproj.nuget.g.targets
 create mode 100644 MyAwesomeApp/obj/project.assets.json
 create mode 100644 MyAwesomeApp/obj/project.nuget.cache
```

Add tag named `v0.0.0` to the commit

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git tag v0.0.0
```

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git tag
v0.0.0
```

After that, we can push it

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git push --atomic origin master v0.0.0
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 12 threads
Compressing objects: 100% (11/11), done.
Writing objects: 100% (11/11), 5.81 KiB | 457.00 KiB/s, done.
Total 11 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), done.
To https://github.com/40843245/GitHub-example-1.git
   db22c10..567a803  master -> master
 * [new tag]         v0.0.0 -> v0.0.0
```

Look at log to ensure that we have successfully pushed it.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git log --oneline
567a803 (HEAD -> master, tag: v0.0.0, origin/master) Part 0: Create a new empty console project
```

In the next section, I will illustrate how to look at PR (pull request), create a new PR in `feature/pull-request-demo` etc.

+ First, we create a branch named `feature/pull-requests-demo` and switch branch.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git checkout -b feature/pull-requests-demo
Switched to a new branch 'feature/pull-requests-demo'
```

+ To look at all open PR.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (feature/pull-requests-demo)
$ gh pr checkout
no open pull requests in 40843245/GitHub-example-1
```

+ To create PR from `feature/pull-requests-demo` branch to `master` branch,

first we need to ensure that there are at least one commits (but unpushed) in `feature/pull-requests-demo` branch or `master` branch.

> [!IMPORTANT]
> Before creating PR from `A` branch to `master` branch,
>
> please always ensure that there are at least one unpushed commits in `A` branch or `master` branch,
>
> otherwise, there will get an error.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (feature/pull-requests-demo)
$ git status
On branch feature/pull-requests-demo
Your branch is up to date with 'origin/feature/pull-requests-demo'.

nothing to commit, working tree clean
```

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (feature/pull-requests-demo)
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
```

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```

Since there are no commits between `feature/pull-requests-demo` branch and `master` branch, let's modify the `MyAwesomeApp/Program.cs` to

```
Console.WriteLine("This is written in 'feature/pull-requests-demo' branch");

```

and then commit it with tag v1.0.1.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (master)
$ git checkout feature/pull-requests-demo
Switched to branch 'feature/pull-requests-demo'
Your branch is up to date with 'origin/feature/pull-requests-demo'.
```

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (feature/pull-requests-demo)
$ notepad "MyAwesomeApp/Program.cs"
```

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (feature/pull-requests-demo)
$ git add .
```

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (feature/pull-requests-demo)
$ git status
On branch feature/pull-requests-demo
Your branch is up to date with 'origin/feature/pull-requests-demo'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   MyAwesomeApp/Program.cs
```

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (feature/pull-requests-demo)
$ git commit -m "Part 1.1: Pratice Create PR"
[feature/pull-requests-demo c141e5a] Part 1.1: Pratice Create PR
 1 file changed, 1 insertion(+), 2 deletions(-)
```

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (feature/pull-requests-demo)
$ git tag v1.0.1
```

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (feature/pull-requests-demo)
$ git  tag
v0.0.0
v1.0.1
```

After that, we can create PR from `feature/pull-requests-demo` branch.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (feature/pull-requests-demo)
$ gh pr create
```

Then it will ask you some question.

For example,

GitHub asks me `Where should we push the 'feature/pull-requests-demo' branch?`

I answer we should push it in remote repo named `GitHub-example-1` in `40843245` GitHub account.

```
? Where should we push the 'feature/pull-requests-demo' branch? 40843245/GitHub-example-1

Creating pull request for feature/pull-requests-demo into master in 40843245/GitHub-example-1
```

Then GitHub asks me the title pf PR

I reponse `practice PR`

```
? Title (required) practice PR
```

Then GitHub asks me the body of PR.

I click keyboard `e` to open notepad and write

```
Practice how to create PR.
```

After that, I save it, close it.

```
? Body <Received>
```

Lastly, I choose to submit

```
? What's next? Submit
branch 'feature/pull-requests-demo' set up to track 'origin/feature/pull-requests-demo'.
To https://github.com/40843245/GitHub-example-1.git
   567a803..c141e5a  HEAD -> feature/pull-requests-demo
https://github.com/40843245/GitHub-example-1/pull/1
```

And I see a PR with id `1` is created, url `https://github.com/40843245/GitHub-example-1/pull/1`

<img width="599" height="466" alt="image" src="https://github.com/user-attachments/assets/9113aa62-f2b9-429a-a80c-b940e77e00a5" />

After I redirect to url `https://github.com/40843245/GitHub-example-1/pull/1` and click `Merge Pull Request` button (with green background) and follows its instruction,

I've merged the PR successfully and, of course, it is closed.

<img width="721" height="488" alt="image" src="https://github.com/user-attachments/assets/5a2d5f46-aec1-45e8-950f-65a0019ef989" />

+ In next section, I'll illustrate that how to open the webbroswer.

To open the webroswer and redirect to the root directory of current working remote repo,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/GitHub (feature/pull-requests-demo)
$ gh browse
Opening https://github.com/40843245/GitHub-example-1 in your browser.

```

<img width="944" height="509" alt="image" src="https://github.com/user-attachments/assets/025e93ba-3176-4b1d-be29-440965813e20" />

To open PR 1 (if PR 1 exists) or the issue 1 (iff issue 1 exists),

```
$ gh browse 1
Opening https://github.com/40843245/GitHub-example-1/issues/1 in your browser.
```

Then we will redirect to `https://github.com/40843245/GitHub-example-1/pull/1` and we will see `PR #1`

<img width="689" height="480" alt="image" src="https://github.com/user-attachments/assets/e01a09a9-92e9-4964-b2ed-e0fd24faa658" />

