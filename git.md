###### UBUNTU 22.04.1 LTS (WSL2)
# **GIT NOTES**
### INSTALLING/UPDATING GIT

Make sure your system is updated:
`sudo apt update && sudo apt upgrade`

Add git's repository:
`sudo add-apt-repository ppa:git-core/ppa && sudo apt update`

Install git:
`sudo apt install git`

Make sure git is installed:
`git --version`

In order to use git without sudo and bad perm management we will mount our Windows drives
under WSL.

Edit/create the file:
`sudo vim /etc/wsl.conf`

Add:
```cmd
[automount]
options = "metadata"
```

Now, either restart your windows machine or close all WSL shells and run `wsl --shutdown`.

### SETTING UP A REMOTE REPO WITH SSH KEYS
`ssh-keygen -o -t rsa -C "email@example.com"` # create a public/private rsa key pair with openssh format
`cd ~/.ssh`	# where the public ssh key is
`cat id_rsa.pub` # view the public key

Now, copy the public key.
Browse to account settings > SSH AND GPG keys > New SSH key and paste the key in.
After adding, use either of the following to create/clone the remote repo:
```cmd
git remote add origin git@github.com:user/repo.git
git clone git@github.com:datowq/guides.git	
```

### USING GIT
**Basic git workflow:**

`git clone <a git repository>` # copy a repo that already exists

OR

`git init` # create a local repo

`git fetch` # fetch contents from a remote repo

`git add <some-file/folder>` # stage a file/folder (use -A or . for everything)

`git status` # view the state of the working directory and staging area

`git commit -m <message>` # commit whatever is staged with a commit message

`git push` # push the committed changes to the desired branch/repo


**For a workflow with a team:**

`git pull <--rebase>` # fetch a remote repo and use rebase or merge to handle merge conflicts

`git status` # show where a merge conflict is

`git add <file/folder>`	# stage the resolved merge conflict

`git rebase --continue` # commit each resolved merge conflict as they are rebased

`git rebase --abort` # reset to before the initial pull

`git push` # push the committed resolved conflicts to the desired branch/repo


**Branching:**

`git branch <name>`	# create a new branch

`git checkout <branch name>` # switch to a branch

`git checkout -b <name>` # switch to and create a new branch

`git branch -d <branch name>` # delete a branch

`git merge <branch name>` # merge the branch with the branch you are currently checked-out to


**Helpful git tools:**

`git log` # view the commit history

`git reset` # unstage all files

`git reset -- <file>` # unstage a specific file

`git reset --soft HEAD~1` # undo the last commit; --soft preserves file changes;--hard and --mixed are options

`git revert HEAD` # revert the last commit and add a new commit to undo the last commit
