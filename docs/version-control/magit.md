# Magit Git client

++spc++ ++"g"++ ++"s"++ to open magit status

Magit Status buffer shows the status of the local and remote repository (when a remote is added)

++question++ to show the Magit Status help


## Navigating Magit Status buffer

++"j"++ / ++"k"++ to navigate line by line

++bracket-left++ / ++bracket-right++ to navigate by section, depending on the type of section the cursor is located (hunk, file, status)

++tab++ to toggle the expantion of the current sections. ++shift++ ++tab++ to toggle the expansion of all sections


## Stage Changes

++"s"++ to stage a file, hunk or visual selection, ++"S"++ to stage all unstaged changes.

++"u"++ to unstage a file, hunk or visual selection, ++"U"++ to unstage all staged changes.

++"v"++ ++"j"++ / ++"k"++ to select one or more lines within a hunk


## Commits

++"c"++ opens the commit menu

* ++"c"++ to create a new commit from the staged changes
* ++"a"++ to amend an existing commit with the staged changes
* ++"e"++ to extend a existing commit with the staged changes (skip editing the commit message)

++"c"++ opens the commit message buffer, using a commit message template if configured

++"a"++ opens the commit message buffer with the message from the current commit

++"Z"++ ++"Z"++ to create a new commit, including any changes maded to the commit message

++"Z"++ ++"Q"++ to abort the commit message

++enter++ on a commit, e.g. in recent commit section, opens the commit details that shows the commit message, meta data and the changes (diff)



## Changing History

The latest commit can be ammended, extended, squashed from the ++c++ commit menu.

++"O"++ on a commit (in recent commits or log view)

++"r"++ rebase menu to change any part of the commit history


## Remote Repositories

++"M"++ opens the remote menu

++"a"++ to add a remote, specifying the name for the remote, e.g. `practicalli`

++"r"++ to rename an existing remote name, prompting to select the remote to rename

++"C"++ to configure an existing remote, i.e. to update the URL of the remote

++"P"++ opens the push menu, ++"p"++ to push all local changes to the remote repository (origin or what ever remote is set as the push default)

++"F"++ opens the pull menu, ++"p"++ to pull remote changes to the local repository, or ++"u"++ to pull from upstream, ++"e"++ to select the remote from those currently added.


## Merge Conflicts

++"e"++ on a conflicted file opens an ediff view, showing the original file on the left and the changes on the right, with a 3rd window at the bottom that contains the ediff commands.

++"j"++ / ++"k"++ to navigate by diff, moving the two main views in unison.

++"a"++ to retain the original text and update the change, or ++"b"++ to accept the new change into the original file

> Pushing changes regularly minimises the risk of merge conflicts



## TODO list

> TODO: is the magit-todo list included in doom or does it need to be added as a package?


## reference

* [Magit key binding reference sheet](https://discourse.doomemacs.org/t/magit-keybind-reference-sheet/473) - Doom discourse
