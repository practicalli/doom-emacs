# Working with Projects

++spc++ ++"p"++ ++"a"++ to add a new project to Doom, selecting the directory path for the root of the project.

++spc++ ++"p"++ ++"p"++ to switch to a project other than the current, list shows all other projects except current project. A project is automatically assigned a workspace when opened. ++spc++ ++tab++ ++"r"++

> TODO: How to delete a project

Each project is automatically opened in a new workspace

++spc++ ++tab++ ++full-stop++ to select a project workspace

++spc++ ++back-tick++ to switch to previous buffer

++spc++ ++tab++ ++back-tick++ to switch to previous workspace

> TODO: paste kill ring cycle - paste transient state in spacemacs

## Discover projects

++spc++ ++"p"++ ++d++ to discover projects withing the directories specified in `projectile-project-search-path`

```emacs
(setq projectile-project-search-path '(("~/projects" . 2) ("~/.config" . 1)))
```

## Files

++spc++ ++"u"++ ++spc++ ++"f"++ ++"f"++

++spc++ ++"f"++ ++"f"++ to open or create a new file. If a file is open in the current buffer, its path is used as the starting point. To create a file (and intermediate directories), type any additional path and file name.

++spc++ ++"p"++ ++"f"++ to list all files in the current project / workspace. Use this when you know the name of the project but not the path or to avoid navigating to the correct path.



??? WARNING "Project Cache Outdated"
    ++spc++ ++"p"++ ++"i"++ to udate the project cache moving directories and files, otherwise Doom will open a buffer for the old location

    ++spc++ ++"u"++ before a file command will also clear the cache and allow correct selection of files, e.g.

    ++spc++ ++"u"++ ++spc++ ++"f"++ ++"f"++


## Windows

++spc++ ++"w"++ and one of ++"h"++ ++"j"++ ++"k"++ ++"l"++ for vim-style navigation of windows

++spc++ ++"w"++ ++"v"++ to create a new vertical window, ++spc++ ++"w"++ ++"h"++ for a new horizontal window

# Sessions

spc q s to save the current session, which should load when (re)starting Emacs

## Searching across a project

++spc++ ++slash++ to search across all files in a project, using ripgrep (if installed on OS execution path)

++ctrl+"c"+ctrl+"e"++ opens search results in a separate buffer for editing results.

++ctrl+"c"+ctrl+"c"++ or ++z++ ++z++ to commit changes


!!! HINT "Narrow search results with Ripgrep switches"
    Use ripgrep switches before or after a search pattern, E.g. #-t clojure -- test or #test -- -t clojure.

    `rg --type-list` for comprehensive list of types supported by Ripgrep.  Types can represent one or more file extensions.

    `#test -- -t clojure`  only search for Clojure files (*.clj, *.cljc, *.cljs, *.cljx file extension )

    `#test -- -g*.tar.gz` - search any file that matches a glob, i.e. file extension .tar.gz

    `#test#!cd` - search for test and filter results containing `cd` using consult sub-search feature

    Everything before the second # is filtered by ripgrep.

    Everything after the second # is filtered by Vertico using Orderless 23, where ! (negatation), = (literal), ~ (fuzzy), % (case insensitive) prefixes are supported.

    ++"#"++ delimiter can be replaced with any arbitrary character. E.g. %test%!cd or *test*!cd, useful when the search pattern starts with a `#` character
