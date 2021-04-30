# Flow
Vendor Code Supported Git Workflow


# Commands
All commands should follow below syntax

> vegit `<command>` [optional arguments]

## Everyone's commands

#
> ### status
> * To see the current status.
> ##### Usage
> * `vegit status`

#
> ### init
> * To initialize a git repository with vegit.
> ##### Usage
> * `vegit init`

#
> ### start
> * To create a new feature branch from `dev` branch. Once executed, a new branch feature_req123 will be created and you are switched in to that branch.
> ##### Usage
> * `vegit start <change_name>`

#
> ### stage
> * The same symantics of git add command. The command is used to stage your code.
> ##### Usage
> * `vegit add <files to add>`

#
> ### unstage
> * The same symantics of git reset command. To command is used to unstage your code in staging area. This command only unstage your code and put them back on your unstaged code.
> ##### Usage
> * `vegit reset <files to add>`

#
> ### commit
> * The same symantics of git commit command. 
> ##### Usage
> * `vegit commit <git commit options>`

#
> ### publish
> * Pushes all your committed changes to your central repository. _(Experimental) Creates pull requests if needed._
> ##### Usage
> * `vegit publish`

#
> ### delete
> * Deletes a branch. Only works on `feature*` or `vendor_merging` branches. No effect on `vendor*`, `dev`, `test`, `master` branches. Delete only your local branch. 
> ##### Usage
> * `vegit delete <branch name>`

#
> ### switch
> * Switches from branch to branch. However, if you have any unstaged code, first you have to either stage, commit, remove (manually) or ignore them before proceeding. 
> ##### Usage
> * `vegit switch <target_branch>`

## Vendor Integrator Commands
#
> ### vendor
> * Perform various vendor specific operations as listed below
> ##### Usage
> * `vegit vendor [add|get]`
> 
> ###### add
>  `vegit vendor add <vendor_name> <remote_git_repo_uri>`
> ###### get
>  `vegit vendor get <release or branch>`

## Vegit Admin Commands
#
> ### inspect
> * Lists down available branches to merge into the branch you are running on. Only works on `dev`, `test`, `master` branches. A readonly command. 
> ##### Usage
> * `vegit inspect <dev|test|master>`

#
> ### promote
> * Selects a list of branches to merge, tries to merge. If fails, reports the errors. 
> ##### Usage
> * `vegit promote <dev|test|master> --notify <a list of branches to promote>`
> 
> * Only works for `dev`, `test`, `master` branches.
> * If `--notify` is mentioned, the branch oweners are notified whether their changes were promoted or not. 

#
> ### tag
> * The same symantics of git tag command. However, the command only works on `dev`, `test`, `master` branches. When you are releasing a code to an environment, you should use this `tag` command to mark it down. Don't forget to use correct branch. 
> ##### Usage
> * `vegit tag <dev|test|master> <tag_text>`
> 
> `tag_text` can only contain alphanumeric charecters, - and _ only. 

## Some other useful commands
#
> ### ignore
> * If you need to ignore a list of file from tracking, you may use this command. There is no any un-ignore command, unless you use a git command to do it. 
> ##### Usage
> * `vegit ignore <files to ignore>`

#
> ### copy
> * To copy files from another branch to current branch. However, if you have any unstaged code, first you have to either stage, commit, remove (manually) or ignore them before proceeding. 
> ##### Usage
> * `vegit copy <files to copy>`

#
> ### remove
> * To remove files from filesysterm and git. This command does not perform `commit` command. Thus, it up to you to commit the removal.
> ##### Usage
> * `vegit remove <files to copy>`

#
> ### rename
> * To rename files from filesysterm and git. This command does not perform `commit` command. Thus, it up to you to commit the renaming.
> ##### Usage
> * `vegit rename <old_name> <new name>`
