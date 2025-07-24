Here's the updated README with a brief about Git tags and commands categorized into their respective sections:

---

# GitHub Commands

## Table of Contents

1. [Initialization](#initialization)
   - [Initialize a GitHub Repository Locally](#initialize-a-github-repository-locally)
2. [Configuration](#configuration)
   - [Configure Git Username and Email](#configure-git-username-and-email)
3. [Staging and Committing](#staging-and-committing)
   - [Add Files to the Staging Area](#add-files-to-the-staging-area)
   - [Add Files to Staging and Commit Directly](#add-files-to-staging-and-commit-directly)
   - [Amend the Latest Commit Message](#amend-the-latest-commit-message)
   - [Revert a Commit](#revert-a-commit)
4. [Branch Management](#branch-management)
   - [Create a Branch](#create-a-branch)
   - [Change Branches](#change-branches)
   - [Delete a Local Branch](#delete-a-local-branch)
   - [Delete a Remote Branch](#delete-a-remote-branch)
   - [List Branches](#list-branches)
   - [Create a New Branch and Checkout to It](#create-a-new-branch-and-checkout-to-it)
   - [Switch Branch Using `git switch`](#switch-branch-using-git-switch)
   - [Merge a Branch with Squashing Commits](#merge-a-branch-with-squashing-commits)
   - [Squash/Rebase Commits into a Branch](#squashrebase-commits-into-a-branch)
5. [Undoing Changes](#undoing-changes)
   - [Undo Changes Using `git reset`](#undo-changes-using-git-reset)
   - [Revert a Commit](#revert-a-commit)
6. [Viewing Changes](#viewing-changes)
   - [See Working Tree Status](#see-working-tree-status)
   - [View Git Logs](#view-git-logs)
7. [Git Tags](#git-tags)

## Initialization

### Initialize a GitHub Repository Locally

To initialize a new GitHub repository locally, use the following command:

```bash
git init
```

[Learn more](https://git-scm.com/docs/git-init)

## Configuration

### Configure Git Username and Email

To add your username and email to your Git configuration, use the following commands:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

[Learn more](https://git-scm.com/docs/git-config)

## Staging and Committing

### Add Files to the Staging Area

To add files to the staging area, use the following commands:

- To add a single file:

  ```bash
  git add filename
  ```

  Replace `filename` with the name of the file you want to add.

- To add all files in the current directory:

  ```bash
  git add .
  ```

  [Learn more](https://git-scm.com/docs/git-add)

### Add Files to Staging and Commit Directly

To add files to the staging area and commit them in a single command, use:

```bash
git commit -am "Commit message"
```

Replace `"Commit message"` with your commit message. This command stages all tracked files and commits them with the provided message.

[Learn more](https://git-scm.com/docs/git-commit#_options)

### Amend the Latest Commit Message

To modify the most recent commit message, use the following command:

```bash
git commit --amend -m "New commit message"
```

Replace `"New commit message"` with the updated message you want to use.

[Learn more](https://git-scm.com/docs/git-commit#_amend)

### Revert a Commit

To revert a specific commit, use the following command:

```bash
git revert commit-hash
```

Replace `commit-hash` with the hash of the commit you want to revert. This command creates a new commit that undoes the changes made by the specified commit.

[Learn more](https://git-scm.com/docs/git-revert)

## Branch Management

### Create a Branch

To create a new branch, use the following command:

```bash
git branch branch-name
```

Replace `branch-name` with the name of the branch you want to create. This command creates a new branch from the current branch but does not switch to it.

[Learn more](https://git-scm.com/docs/git-branch)

### Change Branches

To switch to a different branch, use the following command:

```bash
git checkout branch-name
```

Replace `branch-name` with the name of the branch you want to switch to. This command changes the current working branch to the specified branch.

[Learn more](https://git-scm.com/docs/git-checkout)

### Delete a Local Branch

To delete a local branch, use the following command:

```bash
git branch -d branch-name
```

Replace `branch-name` with the name of the branch you want to delete. If the branch has not been fully merged, you can force delete it with:

```bash
git branch -D branch-name
```

[Learn more](https://git-scm.com/docs/git-branch#_delete_branch)

### Delete a Remote Branch

To delete a remote branch, use the following command:

```bash
git push origin --delete branch-name
```

Replace `branch-name` with the name of the remote branch you want to delete. This command removes the branch from the remote repository.

[Learn more](https://git-scm.com/docs/git-push#_deleting_a_remote_branch)

### List Branches

To list branches, use the following commands:

- **List Local Branches**:

  ```bash
  git branch
  ```

- **List Remote Branches**:

  ```bash
  git branch -r
  ```

- **List All Branches (Local and Remote)**:

  ```bash
  git branch -a
  ```

[Learn more](https://git-scm.com/docs/git-branch)

### Create a New Branch and Checkout to It

To create a new branch and switch to it immediately, use the following command:

```bash
git checkout -b branch-name
```

Replace `branch-name` with the name of the new branch you want to create.

[Learn more](https://git-scm.com/docs/git-checkout#_switching_branches)

### Switch Branch Using `git switch`

To switch branches using `git switch`, use:

- **Switch to an Existing Branch**:

  ```bash
  git switch branch-name
  ```

- **Create and Switch to a New Branch**:

  ```bash
  git switch -c new-branch-name
  ```

[Learn more](https://git-scm.com/docs/git-switch)

### Merge a Branch with Squashing Commits

To merge a branch and squash commits:

1. **Switch to the Target Branch**:

   ```bash
   git switch target-branch
   ```

2. **Merge the Source Branch with Squashing**:

   ```bash
   git merge --squash source-branch
   ```

3. **Commit the Squashed Changes**:

   ```bash
   git commit -m "Commit message for the squashed changes"
   ```

[Learn more](https://git-scm.com/docs/git-merge#_squash)

### Squash/Rebase Commits into a Branch

To squash/rebase commits into a branch:

1. **Switch to the Branch with Commits**:

   ```bash
   git switch branch-name
   ```

2. **Start an Interactive Rebase**:

   ```bash
   git rebase -i HEAD~n
   ```

3. **In the Interactive Rebase Editor**:

   - Change `pick` to `squash` for the commits you want to squash.
   - Save and close the editor.

4. **Edit the Commit Message**:

   - Save and close the editor.

5. **Resolve Conflicts (if any)**:

   ```bash
   git rebase --continue
   ```

   - To abort the rebase:

     ```bash
     git rebase --abort
     ```

6. **Push the Rebased Branch**:

   ```bash
   git push --force
   ```

[Learn more](https://git-scm.com/docs/git-rebase)

## Undoing Changes

### Undo Changes Using `git reset`

To undo changes using `git reset`, use the following commands:

- **Soft Reset**:

  ```bash
  git reset --soft commit-hash
  ```

- **Mixed Reset** (default):

  ```bash
  git reset commit-hash
  ```

- **Hard Reset**:

  ```bash
  git reset --hard commit-hash
  ```

[Learn more](https://git-scm.com/docs/git-reset)

## Viewing Changes

### See Working Tree Status

To see the status of your working tree, use the following command:

```bash
git status
```

[Learn more](https://git-scm.com/docs/git-status)

### View Git Logs

To view the commit history, use the following commands:

- For a concise, one-line-per-commit format:

  ```bash
  git log --oneline
  ```

- For the standard, detailed format:

  ```bash
  git log
  ```

[Learn more](https://git-scm.com/docs/git-log)


## Git Tags

Git tags are used to mark specific points in the commit history as important. They are often used to label release versions (e.g., `v1.0`, `v2.0`). There are two types of tags: lightweight and annotated. Lightweight tags are simply pointers to a commit, while annotated tags store extra metadata like the tagger's name, email, and date.

### Create a Lightweight Tag

To create a lightweight tag, use:

```bash
git tag tag-name
```

Replace `tag-name` with the desired name of your tag.

[Learn more](https://git-scm.com/docs/git-tag#_lightweight_tags)

### Create an Annotated Tag

To create an annotated tag, use:

```bash
git tag -a tag-name -m "Tag message"
```

Replace `tag-name` with the name of the tag and `"Tag message"` with a descriptive message.

[Learn more](https://git-scm.com/docs/git-tag#_annotated_tags)

### List All Tags

To list all tags in your repository, use:

```bash
git tag
```

[Learn more](https://git-scm.com/docs/git-tag#_listing_tags)

### Show Tag Details

To show details about a specific tag, use:

```bash
git show tag-name
```

Replace `tag-name` with the name of the tag you want to view.

[Learn more](https://git-scm.com/docs/git-show)

### Delete a Tag Locally

To delete a tag locally, use:

```bash
git tag -d tag-name
```

Replace `tag-name` with the name of the tag you want to delete.

[Learn more](https://git-scm.com/docs/git-tag#_deleting_tags)

### Delete a Tag Remotely

To delete a tag from a remote repository, use:

```bash
git push origin --delete tag tag-name
```

Replace `tag-name` with the name of the tag you want to delete from the remote repository.

[Learn more](https://git-scm.com/docs/git-push#_deleting_a_tag_from_a_remote)

---

Feel free to let me know if there's anything else you'd like to add or modify!
