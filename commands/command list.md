# command list
## login
+ To login in, type

```
gh auth login
```

## repo
### clone the repo
+ To clone the repo, type with this format

```
gh repo clone (<url>|<username>/<repo-name>)
```

where

`<url>` is the url of the repo to clone it. You can copy the url through clicking the `copy url` icon in `Code` button ->`Local` tab->`HTTPS` tab shown in this figure.

<img width="734" height="450" alt="image" src="https://github.com/user-attachments/assets/4bb75d30-0450-4f96-a755-7431d21f5504" />

`<username>` is the username.

`<repo-name>` is the repo name.

### create a remote repo
+ To create a remote repo, use one of these formats

```
gh repo create (--remote)? <repo-name> <options>? # create a remote repo using current logged-in account
```

or

```
gh repo create (--remote)? <organization-name>/<repo-name> <options>? # create a remote repo using specific organization name
```

or

```
gh repo create ((-h|--homepage) <url>) <options>?
```

In the first form,

```
gh repo create (--remote)? <repo-name> <options>?
```

It will create a repo named `<repo-name>` in current logged-in account with these options `<options>` (if supplied).

In the second form,

```
gh repo create (--remote)? <organization-name>/<repo-name> <options>?
```

It will create a repo named `<repo-name>` in the organization named `<organization-name>` with these options `<options>` (if supplied).

> [!NOTE]
> You can't create repo the specific account directly using `gh repo create`
>
> If you want to do so,
>
> you have to login or switch account then directly create the repo using the first form.
>
> For more details, see [Google Gemini's response](https://gemini.google.com/share/975634788f71)

or use the third form iff you are familiar with the url routing and willing to supply the url as remote repo name. 

> [!NOTE]
> In the first and second form, if you supply `--remote` long option, you can move it in `<options>`,
>
> making, for example,
>
> ```
> gh repo create --public --remote "git-example-1"
> ```
>
> which is equivalent to
>
> ```
> gh repo create "git-example-1" --public
> ```

> [!NOTE]
> In the third form, if you supply `--homepage` long option or `-h` short option, you can move it in `<options>`,
>
> making, for example,
>
> ```
> gh repo create --public -h "https://github.com/40843245/git-example-1.git"
> ```
>
> which is equivalent to
>
> ```
> gh repo create -h "https://github.com/40843245/git-example-1.git" --public
> ```

+ To supply that we want to create a public remote repo, please supply `--public` long option in `<options>`
+ To supply that we want to create a private remote repo, please supply `--private` long option in `<options>`
+ To supply that source path of local repo, please supply `--source` long option with source path in `<options>`

> [!NOTE]
> The `--public` long option and `--private` long option are mutally exclusive. A repo can't be public and private at same time.

> [!NOTE]
> If neither `--public` long option nor `--private` long option are supplied, it uses the default `--public`.

> [!NOTE]
> If `--source` long option is NOT supplied, it uses the default source path `.` (i.e. current working directory).

For more available option, see [GitHub CLI docs#gh repo create](https://cli.github.com/manual/gh_repo_create)

### list repos
Format:

```
gh repo list <owner>? <options>?
```

where 

`<owner>`: owner (i.e. user or organization) 

or use its alias

```
gh repo ls
```

(as `gh repo list`)

+ To list all repos in current logged in account, NOT supply the `<owner>`

```
gh repo list
```

We can filter using options `<options>`

For available options, see [GitHub CLI docs#gh repo list](https://cli.github.com/manual/gh_repo_list)

### edit repo
+ To edit repo, use these format,

```
gh repo edit <repo-name>? <options>
```

where

`<repo-name>`: the repo name.

If the repo name `<repo-name>` is NOT supplied, the current working repo will be used.

For available options, see [GitHub CLI docs#gh repo edit](https://cli.github.com/manual/gh_repo_edit)

## PR (pull request)
### create PR
To create PR interactively, type

```
gh pr create
```

Then the terminal will ask you some important questions (such as PR title, PR body). Please give a brief and clear response.

## alias
### set an alias
+ To give an alias, use `gh alias set` using these formats

```
gh alias set <alias-name>='<command-to-be-executed>'
```

where

`<alias-name>` : a descriptive name of the alias

`<command-to-be-executed>`: command that will be executed once the alias is used.

> [!NOTE]
> On Window Command Prompts, it is always needed to quotate the `<command-to-be-executed>`.

For more detailsm see [GitHub CLI docs#gh alias set](https://cli.github.com/manual/gh_alias_set)

### list all alias
+ To list all aliases, use

```
gh alias list
```

or it alias

```
gh alias ls
```
