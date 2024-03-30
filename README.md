#### Git Commands (tutorial 1):
1. `git init`
2. `git add`
3. `git status`
4. `git commit -m`
5. `git log`
6. `git reset`
8. `git checkout `
9. `q`- quits
10. `z` - clicking this after `typing git log` scrolls down to older versions
11. `git log --all`
12. `git log --all --graph`
13. `git checkout ... filename` - helps us to restore specific or all files from other versions
14. `git config --global alias.s "status" ` - this is how we set or replace existing alias (shortcuts) for git. Here we set shortcut for status to "git s"
15. `git config --get-regexp ^alias` - displays all created alias
16. `.gitignore` -  in this file we write files that we want to ignore for version history. **We add and commit gitigore file too to intitialize it**
17. `rm -rf .git` - removes git from your projects and you should type it in ``git bash``. **don't do this unless you copy existing project**

#### Git Commands (tutorial 2):
1. `git remote add origin (or any name) https (of remote repo)` - to link local with remote repository. Example: `git remote add origin https://github.com/islom2202/tutorials.git`.
2. `git remote` or `git remote -v` - to verify if we have already connected to a remote repository, the second is for more detailed verification
3. `git remote remove origin (or any name)` - to disconnect from remote repository 
4. `git config --global credential.username (username)` - STILL DO NOT EXACTLY KNOW WHAT THIS IS ACTUALLY FOR.
5. `git config --list` - displays the list of all settings.
6. `git push origin main` - pushes only commits, not staged, working changes, or amends to a main branch of a remote repository
8. `git commit --amend` usually cannot be pushed, therefore to pass this we should add `-f`, which means force push like this: 
     - **git push origin main -f**
9. `"git push -u origin main"` or `"git push push origin main --set-upstream"` - both establish a connection between the local branch and the remote branch, allowing for easier tracking and synchronization of changes, so there would be no need to type origin main again.
10. `git clone (https) (type to create foldername)` - to clone a repository from github
11. `git fetch` - This command retrieves changes from the remote repository to your local repository without merging them into your current working directory.
12. `git pull` - not only fetches the changes from the remote repository but also directly integrates them into your current working copy files. It is a combination of **git fetch** and either **git merge** 
13. How to generate SSH (for more info read doc from <a href="https://docs.github.com/en/authentication/connecting-to-github-with-ssh">Github SSH Docs</a>):
     1. Open Git Bash:
     2. Enter ``ls -al ~/.ssh`` to see if existing SSH keys are present.
     3. Check the directory listing to see if you already have a public SSH key. By default, the filenames of supported public keys for GitHub are one of the following: 
         - id_rsa.pub
         - id_ecdsa.pub
         - id_ed25519.pub
     4. If there is no any public SSH key, type this, replacing the email used in the example with your GitHub email address and keep clicking enter twice: <br>
         ~~~
         ssh-keygen -t ed25519 -C "your_email@example.com"
         ~~~
     5. Type this and enter and it generates SSG key in your clipboard: 
        ~~~
        clip < ~/.ssh/id_ed25519.pub
        ~~~
     6. Go to ``Gitub account``, click on ``settings``, select ``SSH and GPG keys``, click on ``New SSH key``, ``give any title``, paste SSH key into ``key textarea``, click on ``Add SSH key``.
     7. Then to test it, clone the project from remote repository using SSH and enter this to check if it exists.: 
          ~~~
          ls -al ~/.ssh
          ~~~

#### Git Branching anf Merging (tutorial 3):
1. `git branch -M brachname` - to name a main branch
2. `git branch brachname` - to add a new branch.
3. `git checkout brachname` - to switch to a branch
4. `git merge brachname -m "" ` - to merge a branchname into a current branch.
5. `git push origin --delete branchname` - to delete a branch from a remote repository
6. `git branch -d branchname` - to delete a merged branch from a local repository
7. `git branch -D branchname` - to delete a unmerged branch from a local repository