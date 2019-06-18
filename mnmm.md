# version Control system:

Version Control is the management of changes to documents, computer programs, websites or other collection of information. It is also known as Revision Control or Source Code Management.

This changes are often identified as numbers or letter code, termed as revision number. Each revision is associated with meta data like timestamp, author, etc. Revisions can be compared, restored or merged.

**Important of version control system**

Version control is important for today's development teams. It needs to do more than just manage and track files. It should help you develop and ship products faster. This is  especially important for teams practicing DevOps.

That's because using the right version control:

- Improves visibility.
- Helps teams collaborate around the world.
- Accelerates product delivery.

## How to clone a Git repository:

###### You can use Sourcetree, Git from the command line, or any client you like to clone your Git repository. These instructions show you how to clone your repository using Git from the terminal.

1. From the repository, click **+** in the global sidebar and select **Clone this repository** under **Get to work**.

2. Copy the clone command (either the SSH format or the HTTPS).
   If you are using the SSH protocol, ensure your public key is in Bitbucket and loaded on the local system to which you are cloning.

3. From a terminal window, change to the local directory where you want to clone your repository.

4. Paste the command you copied from Bitbucket, for example:

   CLONE OVER HTTPS:

   ```none
    $ git clone https://username@bitbucket.org/teamsinspace/documentation-tests.git
   ```

   CLONE OVER SSH:

   ```none
   $ git clone ssh://git@bitbucket.org:teamsinspace/documentation-tests.git
   ```

If the clone was successful, a new sub-directory appears on your local drive in the directory where you cloned your repository. This directory has the same name as the Bitbucket repository that you cloned. The clone contains the files and metadata that Git requires to maintain the changes you make to the source files.

## How to push/pull Git repository:

Useing `git push` to push commits made on local branch to a remote repository.

The `git push` command takes two arguments:

- A remote name, for example, `origin`
- A branch name, for example, `master`

For example:

```shell
git push  <REMOTENAME> <BRANCHNAME> 
```

As an example, usually run `git push origin master` to push local changes to online repository.

### **Renaming branches**

To rename a branch, we use the same `git push` command, but we would add one more argument: the name of the new branch. For example:

```shell
git push  <REMOTENAME> <LOCALBRANCHNAME>:<REMOTEBRANCHNAME> 
```

This pushes the `LOCALBRANCHNAME` to your `REMOTENAME`, but it is renamed to `REMOTEBRANCHNAME`.

### **Dealing with "non-fast-forward" errors**

If your local copy of a repository is out of sync with, or "behind," the upstream repository you're pushing to, you'll get a message saying `non-fast-forward updates were rejected`. This means that you must retrieve, or "fetch," the upstream changes, before you are able to push your local changes.

For more information on this error, see "[Dealing with non-fast-forward errors](https://help.github.com/en/articles/dealing-with-non-fast-forward-errors)."

### Pushing tags

By default, and without additional parameters, `git push` sends all matching branches that have the same names as remote branches.

To push a single tag, you can issue the same command as pushing a branch:

```shell
git push  <REMOTENAME> <TAGNAME> 
```

To push all your tags, you can type the command:

```shell
git push  <REMOTENAME> --tags
```

### Deleting a remote branch or tag

The syntax to delete a branch is a bit arcane at first glance:

```shell
git push  <REMOTENAME> :<BRANCHNAME> 
```

Note that there is a space before the colon. The command resembles the same steps you'd take to rename a branch. However, here, you're telling Git to push *nothing* into `BRANCHNAME` on `REMOTENAME`. Because of this, `git push`deletes the branch on the remote repository.

### Remotes and forks

You might already know that [you can "fork" repositories](https://guides.github.com/overviews/forking/)on GitHub.

When you clone a repository you own, you provide it with a remote URL that tells Git where to fetch and push updates. If you want to collaborate with the original repository, you'd add a new remote URL, typically called `upstream`, to your local Git clone:

```shell
git remote add upstream  <THEIR_REMOTE_URL> 
```

Now, you can fetch updates and branches from *their* fork:

```shell
git fetch upstream
# Grab the upstream remote's branches
> remote: Counting objects: 75, done.
> remote: Compressing objects: 100% (53/53), done.
> remote: Total 62 (delta 27), reused 44 (delta 9)
> Unpacking objects: 100% (62/62), done.
> From https://github.com/octocat/repo
>  * [new branch]      master     -> upstream/master
```

When you're done making local changes, you can push your local branch to GitHub and [initiate a pull request](https://help.github.com/en/articles/about-pull-requests).



## How to check the status of the repository: 

Use the `git status` command, to check the current state of the repository.

#### *RUN:</u>*

```
git status
```

You will see

#### *RESULT:*

```
$ git status
# On branch master
nothing to commit (working directory clean)
```

The command checks the status and reports that there’s nothing to commit, meaning the repository stores the current state of the working directory, and there are no changes to record.

We will use the git status, to keep monitoring the states of both the working directory and the repository.

# How to create and switch to a branch:



Each time you want to commit a bug or a feature, you need to create a branch for it.

To create a new branch there is a `git branch` command.

After you have created a branch, you need to switch in this branch using a `git checkout` command.

But it is also possible to create a new Git branch and switch in this branch using only one `git checkout` command with `-b` option.

Create a new Git branch and checkout:

```
$ git branch <branch_name>
$ git checkout <branch_name>
```

Create a Git branch and checkout in one command:

```
$ git checkout -b <branch_name>
```

  

# How to connect to a remote a repository:

When you clone a repository from a remote server, Git automatically remembers this connection for you. It saves it as a remote called "origin" by default.
In other cases where you started with a fresh local repository, no remote connections are saved. In that situation, we need to connect our local repository to a new remote before we can try some remote interactions:

```
$ git remote add crash-course-remote 
    https://github.com/gittower/git-crash-course-remote.git
```

Let's check if this worked out ok:

```
$ git remote -v
crash-course-remote   https://github.com/gittower/git-crash-course-remote.git (fetch)
crash-course-remote   https://github.com/gittower/git-crash-course-remote.git (push)
origin   https://github.com/gittower/git-crash-course (fetch)
origin   https://github.com/gittower/git-crash-course (push)
```

Note that each remote repository consists of two lines: the first one is the "fetch URL" 

# How to merge two branch:

