<h1 align="center">GIT training</h1>

<p align="center"><img src="GIT_bash.PNG" alt="Logo" width="500" height="350"></p>

You can download Git here: [Git SCM Downloads](http://git-scm.com/downloads) and install it with the default settings.

### Generating a Pair of SSH Keys

```sh
ssh-keygen -t rsa -C "korWIN@winwin.com"
```

The public key (`id_rsa.pub`) should be sent to the owner of the repository to obtain work rights, or uploaded to profile settings in Bitbucket, GitHub, or GitLab.

### Username and Email Settings

```sh
git config --global user.name "Janusz Korwin-Mikke"
git config --global user.email "korWIN@winwin.com"
```

## Adding Changes

### Staging Files

- To add all changed files to the commit:

  ```sh
  git add .
  ```
<p align="center"><img src="git_add.PNG" alt="Logo" width="500" height="350"></p>

- To add a specific file:

  ```sh
  git add song.txt
  ```

### Committing Changes

```sh
git commit -m "Describe the changes here"
```

## Git GUI Tools

- To use the Git GUI instead of the terminal:

  ```sh
  git gui &
  ```

<p align="center"><img src="GIT_gui.PNG" alt="Logo" width="500" height="350"></p>


- To open a window showing all commits:

  ```sh
  gitk &
  ```

<p align="center"><img src="GITk&.PNG" alt="Logo" width="500" height="350"></p>

## Reverting Changes

### Working Directory

- Discard changes in a specific file:

  ```sh
  git checkout -- file.txt
  ```

- Discard all local changes:

  ```sh
  git checkout .
  ```

- Remove untracked files and directories:

  ```sh
  git clean -xdf
  ```

### Staging Area (Index)

- Unstage a file:

  ```sh
  git reset file.txt
  ```

  ```sh
  git reset --soft HEAD~1
  ```

<p align="center"><img src="reset_soft.PNG" alt="Logo" width="380" height="290"></p>

  ```sh
  git reset --mixed HEAD^
  ```

<p align="center"><img src="reset_mixed.PNG" alt="Logo" width="380" height="290"></p>

### Local Branch

- Move HEAD back by two commits:

  ```sh
  git reset HEAD^^  # Equivalent to HEAD~2
  ```

- Amend the last commit:

  ```sh
  git commit --amend -m "Updated commit message"
  ```

### Remote Repository

- Revert a specific commit (already commited to the remote repo) by creating a new commit that undoes the changes:

  ```sh
  git revert <commit-hash>
  ```



## Branch and Merge 


#### Listing Branches
To see all the branches in your repository
```sh
git branch
```
The branch you're currently on will be marked with (`*`).

#### Creating a New Branch
To create a new branch and switch to it at the same time, you can run the git checkout command with the -b switch
```sh
git checkout -b [branch-name]
```

#### Switching Branches
To change to another branch and update your working directory
```sh
git checkout [branch-name]
```
<p align="center"><img src="git_checkout.PNG" alt="Logo" width="500" height="350"></p>

#### Merging Branches
To merge the changes from a specified branch into your current branch
```sh
git merge [branch]
```
<p align="center"><img src="git_merge.PNG" alt="Logo" width="500" height="350"></p>

Rebase your current branch onto another branch
- IT SHOULD ONLY BE USED WHEN WORKING ON A SMALL BRANCH
```sh
git rebase [base-branch]
```
This command will move the base of your current branch to the tip of the specified base branch.

#### Viewing Commit History
To display the complete commit history of the current branch
```sh
git log
```

## .gitignore Guidelines

<p align="center"><img src="ignore.PNG" alt="Logo" width="500" height="350"></p>

#### Cherry-picking

- Find the Commit You Want to Pick
(Use git log or git reflog to find the commit hash you want to cherry-pick)
```sh
git log --oneline
```

- Example output:
```sh
a1b2c3d Fixed this sexy bug
e4f5g6h Add new feature
i7j8k9l Update README
```

- Copy the commit hash (e.g., a1b2c3d)

- Switch to the Target Branch
(before applying the commit, switch to the branch where you want to apply the commit)
```sh
git checkout target-branch
```

 Apply the Commit Using Cherry-Pick
```sh
git cherry-pick a1b2c3d
```
