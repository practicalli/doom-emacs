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


# Sessions 

spc q s to save the current session, which should load when (re)starting Emacs
