# Git Commands
Git is a distributed version-control system for tracking changes in source code during software development. It is designed for coordinating work among programmers, but it can be used to track changes in any set of files. Its goals include speed, data integrity, and support for distributed, non-linear workflows.

At Shift3, we use git for a majority of our software projects.

## Shift3 git specific resources
1. [Commits](standards/commits.md)
2. [Branching](standards/branching.md)
3. [Code Versioning](standards/code-versioning.md)

### Lesser known git commands

#### Git Stash
[git-stash](https://git-scm.com/docs/git-stash): `git stash` is used to record the current state of the working directory and index (your code within your current branch) but want to go back to a clean working directory. In order to "stash" your code away for future use, first `git add` the files you want to stash away but *do not use git commit*. You use the `git stash push` command to create your stash. You can switch your branches and then apply the same code to the new branch with `git stash pop`. 

In the below example, we are pushing this readme into our `foo-999-big-feature` branch which leaves us with a clean working directory/index within our origional branch `mac-192-lesser-known-git`.
```shell
$ git add standards/git-commands.md
$ git stash push
Saved working directory and index state WIP on mac-192-lesser-known-git: 60a39ed Merge remote-tracking branch 'origin/master' into mac-192-lesser-known-git
$ git checkout foo-999-big-feature
$ git stash pop
On branch mac-test-branch
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   standards/git-commands.md

Dropped refs/stash@{0} (1a5b247bdd51df733d9ab2e1d1aadc270eded2ce)
```

A good visual representation can be seen with Gitkrakens documentation: https://support.gitkraken.com/working-with-commits/stashing/