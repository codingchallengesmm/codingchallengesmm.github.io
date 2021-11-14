# How to host your website for free on github pages

## Prerequisites

1. GitHub Account
2. Git
3. VSCode or any other editor / IDE

# 1. Create a repo on GitHub

The repo name has to be `<username>.github.io`. Since my username is `codingchallengesmm`, my repo name is `codingchallengesmm.github.io`.


# 2. Clone the repo

From the terminal or VSCode's terminal, clone the repo:

`git clone <repo-url>`

For example

`git clone https://github.com/codingchallengesmm/codingchallengesmm.github.io.git`

*cd* into the directory:

`cd <repo-name>`

# 3. First commit

*If you've set up your git and ssh keys / PAT before, skip this section.*

Make a change to README.md and save it. Run `git status` to see your change.
```
> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Run `git add -A` to add the change.
Run `git commit -m "first commit"` to commit the changes to your repo.

## 3.1 Set username / email
If it's your first time using git, you'll need to set your name and email.

```
*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

Omit --global to set the identity only in this repository.
```

Run the above commands and try to push to the repo. Git should ask you for your username and password.

```
> git push
Username for 'https://github.com': <your-username>
```

Enter your username. Git will ask you for your password. For example:

```
git push
Username for 'https://github.com': codingchallengesmm
Password for 'https://codingchallengesmm@github.com':
```

Do not enter your password. Instead, you'll need to create an Personal access token.

## 3.2 Create a Personal Access Token

To make changes to your repo, you'll need to set up ssh keys, or PAT (Personal Access Token).

I'll show you how to set up PAT.
1. Go to your github settings
2. Go to Developer Settings
3. Under Personal access tokens, generate a new token
4. Set an expiration date, for example 30 days
5. Check the `repo` checkbox
6. Click generate token at the bottom
7. Copy the token and paste it instead of your password.

```
git push
Username for 'https://github.com': <your-username>
Password for 'https://codingchallengesmm@github.com': <your-personal-access-token>
```

If all goes well, you should see the message similar to this:

```
Enumerating objects: 9, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 12 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 1.68 KiB | 1.68 MiB/s, done.
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), done.
To https://github.com/codingchallengesmm/codingchallengesmm.github.io.git
```

# TroubleShooting

If you could not authenticate with github with your PAT, you could try this:

Change your remote url to `https://<your-username>:<your-personal-access-token>@github.com/<your-username>/<your-username>.github.io.git`.

In my case, the url is: `https://codingchallengesmm:ghp_THISISAFAKEKEY@github.com/codingchallengesmm/codingchallengesmm.github.io.git`

Set the url with the command:
`git remote set-url origin https://codingchallengesmm:ghp_THISISAFAKEKEY@github.com/codingchallengesmm/codingchallengesmm.github.io.git`

or you can also edit the `.git/config`. For VSCode, run this in your vscode:

```
code .git/config
```
Under `[remote "origin"]` change the url to include your access token.

# Socials

Find us on [Facebook](https://fb.me/codingchallengesmm).
