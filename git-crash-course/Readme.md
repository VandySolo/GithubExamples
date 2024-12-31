## Git Hidden Folder

There is a hidden folder called `.git` which tells you that our project is a git repo. 

if we wanted to create a git repo in a new project we create the folder and the initalize that repor using    `git init`


```
mkdir / worspaces/tmp/new-project
cd / worspaces/tmp/new-project
git init
touch Readme.md
code Readme.
git status
git add Readme.md

# make changes to readme.md
git commit -a -m "add readme file"

git init
```

## Cloning

we have three ways to clone, HTTPs , SSH and Github CLI 

Since we are using Github CodeSpaces we'll be creating a temporary directory in our workspace.

```sh 
mkdir /workspace/tmp
cd /workspace/tmp

```

### HTTPS

```sh 
git clone https://github.com/VandySolo/Github-Examples.git 

cd Github-Examples
```
### SSH

```
git@github.com:VandySolo/GithubExamples.git
cd GithubExamples
```

we will need to create our own SSH rsa key pair

```sh
sshe-keygen -t rsa
```
For WSl users and if you create a non default key you might need to add it.

```sh
 eval `ssh-agent`
 ssh-add /home/andrew/.ssh/alt-github_id_rsa
```


### Github-CLI

Install the CLI
eg (Linux) Ubuntu
```sh
(type -p wget >/dev/null || (sudo apt update && sudo apt-get install wget -y)) \
	&& sudo mkdir -p -m 755 /etc/apt/keyrings \
        && out=$(mktemp) && wget -nv -O$out https://cli.github.com/packages/githubcli-archive-keyring.gpg \
        && cat $out | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
	&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
	&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
	&& sudo apt update \
	&& sudo apt install gh -y

```
Once this is installed. 
```sh
gh auth login
gh repo clone VandySolo/GithubExamples

So here we still have to use the 

```

## commits 
When we want to commit code we can write git commit which will open up the commit edit message in the editor of your choice.

```sh
git commit
```
Set the global editor

```sh 
git config --global core.editor emacs 
```
Make a commit and commit message without opening an editor. 
```sh
git commit -m "add another exvlamation " 
```

## Branches

List of branches
```
git branch
```
create a new branch

```
git branch branch-name
```

checkout the branch

```
git checkout dev
```
## Remotes

we can add remote but often you will jsut add remote via upsteam when adding a branch

```sh

git remote add .
git branch -u origin new-feature.
```
## Staching

```sh
git stash list
git stash
git stash save my-name
git stash apply
git stash pop


```

## Merging

```
git checkout dev
git merge main
```


## Add 
When we want to stage changed that will be included in the commit. We can use the add all possible files. 

## Reset 

Reset allows you to move Stage changes to be Unstaged. This is usefull when you want to revert all files not to be committed. 

```sh
git add. 
git reset
```
> git reset will revet a git add. 

## Status

Git status shows you what files will or will not be commited. 

```sh
git status
```


## Gitconfig file

The gitconfig file is what stores your global configuration for git such as email, name , editor and more.

Showing the content of our .gotconfig file

```sh 
git config --list
```


When you first install git you need to suppoes to set up your name and email.

You shoudl have done this 
```
user.name=VandySolo
user.email=bodybuilder27684@gmail.com
```

