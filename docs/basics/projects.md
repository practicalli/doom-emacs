# Working with Projects

++spc++ ++"p"++ ++"a"++ to add a new project to Doom, selecting the directory path for the root of the project.

++spc++ ++"p"++ ++"p"++ to switch to a project other than the current, list shows all other projects except current project.  A project is automatically assigned a workspace when opened.  ++spc++ ++tab++ ++"r"++

> TODO: How to delete a project


Each project is automatically opened in a new workspace

++spc++ ++tab++ ++full-stop++ to select a project workspace

++spc++ ++back-tick++ to switch to previous buffer

++spc++ ++tab++ ++back-tick++ to switch to previous workspace


> TODO: paste kill ring cycle - paste transient state in spacemacs



## Discover projects

++spc++ ++"p"++ ++d++ to discover projects withing the directories specified in `projectile-project-search-path`

```lisp
(setq projectile-project-search-path '(("~/projects" . 2) ("~/.config" . 1)))
```


## Files

++spc++ ++"u"++ ++spc++ ++"f"++ ++"f"++

++spc++ ++"f"++ ++"f"++ to open or create a new file.  If a file is open in the current buffer, its path is used as the starting point.  To create a file (and intermediate directories), type any additional path and file name.

++spc++ ++"p"++ ++"f"++ to list all files in the current project / workspace.  Use this when you know the name of the project but not the path or to avoid navigating to the correct path.


!!! WARNING "Project Cache Outdated"
    Project cache should be refreshed when moving directories and files otherwise Doom may try to open a file from an old location
    ++spc++ ++"u"++ before a file command to clear the cache, e.g.

    ++spc++ ++"u"++ ++spc++ ++"f"++ ++"f"++



## Windows

++spc++ ++"w"++ and one of ++"h"++ ++"j"++ ++"k"++ ++"l"++ for vim-style navigation of windows

++spc++ ++"w"++ ++"v"++ to create a new vertical window, ++spc++ ++"w"++ ++"h"++ for a new horizontal window


# Sessions

spc q s to save the current session, which should load when (re)starting Emacs



## Searching across a project

++spc++ ++slash++ to search across all files in a project, using ripgrep (if installed on OS execution path)


Search & Replace: C-cC-e after a search command to activate wgrep-mode. Now you may edit the results. Later, press C-cC-c (or ZZ , for evil users) to commit your changes.

++ctrl+"c"+ctrl+"e"++ opens search results in a separate buffer for editing results.

++ctrl+"c"+ctrl+"c"++  or ++z++ ++z++ to commit changes
