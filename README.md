# Git Training

## Git Setup Highlights

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

<p align="center"><img src="GIT_gui.png" alt="Logo" width="600" height="400"></p>


- To open a window showing all commits:

  ```sh
  gitk &
  ```

<p align="center"><img src="GITk&.PNG" alt="Logo" width="600" height="400"></p>

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

### Local Branch

- Move HEAD back by two commits:

  ```sh
  git reset HEAD^^  # Equivalent to HEAD~2
  ```

- Amend the last commit:

  ```sh
  git commit --amend -m "Updated commit message"
  ```

## Remote Repository

- Revert a specific commit by creating a new commit that undoes the changes:

  ```sh
  git revert <commit-hash>
  
