# Misc Documents

### What to add to `git/config`
```
[remote "curseforge"]
	url = git@git.curseforge.net:wow/REPOSITORY/mainline.git
	fetch = +refs/heads/*:refs/remotes/curseforge/*
```

### How to upload release version to CurseForge 
```
git tag -a 60200.1 -m "60200.1"
git push curseforge --tags
```
http://wow.curseforge.com/wiki/repositories/repository-faq/

## Curseforge
- Create a project if you haven't already, wait for an admin to approve your project.
- On your project page, you should go to Repository Actions -> Edit Repository.
- For "Repository Type", select the one you want. Currently Subversion, Git, and Mercurial are supported.
- In "Package As", put the name of your project's main folder. For World of Warcraft, this will be the same as your Addon's TOC.
- Wait roughly a minute, and your repository should be created.

### Git
- Follow the instructions of the article about SSH Public Keys.
- Go to your project page and it will list your "Development url". This is what you will be pushing to. ''Note: If you have a pre-1.6.2 version of Git, you can't clone the repository if it's empty, you'll have to push to it first.''
- `mkdir REPOSITORY` (Or whatever your project's name is)
- `cd REPOSITORY`
- `git init`
- `git remote add curseforge git@git.curseforge.net:wow/REPOSITORY/mainline.git` (Whatever your "Development url" actually is.)
- Add whatever files you want, commit it locally
- `git push curseforge master` (Note: If you are using OpenSSH you need to push from Git Bash)
