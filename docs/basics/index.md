# Basic usage


## Line numbers

++spc++ ++"t"++ ++"l"++ toggles consecutive line numbers 

`display-line-numbers-type` set to relative for Vim-style relative numbers, to support jumping lines, e.g. ++2++ ++4++ ++j++
Enable relative line numbers
```emacs title=".config/doom/config.el"
(setq display-line-numbers-type 'relative)
```

## Enable features

`.config/doom/init.el` updated in [practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config)

| feature          | Description                              |
|------------------|------------------------------------------|
| word-wrap        | soft wrapping with language-aware indent |
| multiple-cursors | editing in many places at once           |
|                  |                                          |



## Personal information


```emacs
(setq auth-sources '("~/.authinfo.gpg")
      auth-source-cache-expiry nil) ; default is 7200 (2h)
```


## buffers

new buffers in org-mode than fundamntal-mode, hence

```emacs
(setq-default major-mode 'org-mode)
```


## Spacemacs to Doom Emacs


Layouts -> workspaces

Adding a project seems to add a workspace

`SPC TAB .` to switch between workspaces


## Multiple cursors

> TODO: define key bindings for multiple cursors 

- mc/edit-lines  - create a cursor on every line in the visual selection region - `g r I` in Spacemacs  
- mc/keyboard-quit - cancel multiple cursors - `C-g`


## Rename files

`SPC f f` 

> add a space to the end of the name to ensure Emacs creates a new file rather than selecting the existing name... TODO: is this to be expected
