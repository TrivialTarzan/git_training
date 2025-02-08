# git_training

Git setup highlights

You can download git here: http://git-scm.com/downloads
Install Git with default settings.

Generating a pair of ssh keys:
     ssh-keygen -t rsa –C “vitali_shulha@epam.com"

The public key (id_rsa) should be sent to the owner of the repository in order to obtain work rights. Or upload to profile settings in bitbucket / github / gitlab.
Username and email settings:

     git config --global user.name “Janusz Korwin-Mikke“

     git config --global user.email “korWIN@winwin.com"

You can add changes with this command:
     # write this if you want to add all the changed files to the commit
     git add .

     # wite this to add anly specified file
     git song.txt 

To commit write
     git commit -m "Describe the changes here"

To use the GIT GUI instead of terminal, write in GIT terminal:
     git gui&

To open a window where you'll see all the commits that were made:
     gitk&
     
                    
Rewerting the changes

Git workflow:

Working Directory:

git checkout -- file.txt
This command discards changes you've made to file.txt in your working directory and reverts it to the version in the staging area (or the last commit if not staged). In the diagram, it visually represents moving changes out of the FILE SYSTEM.

git checkout . 
This command discards all local changes in your working directory and reverts them to the state in the staging area (or last commit). It similarly moves changes out of the FILE SYSTEM.

git clean -xdf
This command removes untracked files and directories from your working directory (files that are not under Git's version control). It cleans up your working directory, removing elements not tracked in Git.


Staging area (Index):

git reset file.txt 
This command unstages file.txt. It removes file.txt from the staging area, but it does not discard changes you've made in your working directory to file.txt. 


Local branch:

git reset HEAD^^ (HEAD~2) 
This command moves the current branch's HEAD pointer (and branch pointer) back by two commits. HEAD^^ and HEAD~2 are equivalent ways to reference two commits before the current HEAD. This effectively rewrites the commit history locally by removing the last two commits from the branch. 

git commit --amend -m "commit message" 
This command amends the last commit. It allows you to modify the previous commit's message or even stage changes and incorporate them into the last commit, effectively rewriting the last commit. This also changes the COMMIT history.


Remote repository:

git revert <sha1> 
This command creates a new commit that reverts the changes introduced by the commit specified by <sha1>. It does not rewrite history but instead adds a new commit that undoes a previous one. The diagram suggests it affects the REMOTE REPOSITORY by creating an operation to undo changes from it.