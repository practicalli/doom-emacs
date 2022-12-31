# Doom Emacs configuration

Doom curates a large number of modules, a module being one or more Emacs packages with configuration.

`~/.config/doom/` contains three configuration files created by the install process.

* init.el - enable / disable Doom modules
* config.el - elisp configuration, setting variables, etc.
* packages.el - manage specific packages, adding to or overriding packages in the Doom modules


??? HINT "Check parens are balanced in config"
`check-parens` command will check the current buffer for balanced parens (all open parens have a matching close paren)


## Doom modules

++spc++ ++"h"++ ++"d"++ ++"m"++ to see the built-in documentation for a Doom module (NOTE: documentation can be light or non-existant)


## Line Numbers

`display-line-numbers-type` configures the type of line numbers

- `nil` consecutive line numbering, 1,2,3,...
- `relative` relative numbers to current line for vim navigation, e.g. `24 j` to jump down 24 lines.

```emacs title="~/.config/doom/config.el"
(setq display-line-numbers-type 'relative)
```



## Frames

++spc++ ++"t"++ ++f++ toggles the current frame to be full screen

> TODO: is there a setting to open Doom Emacs in full screen


Configure Emacs to always start maximized
```lisp title="~/.config/doom/config.el"
(add-to-list 'default-frame-alist '(fullscreen . maximized))
```


## Theme

++spc++ ++"h"++ ++t++ opens a selection menu of all available themes.  Type a theme name or scroll with ++ctrl+"j"++ and ++ctrl+"k"++

++enter++ to select the theme.

doom-gruvbox theme is configured in [practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config){target=_blank}

```emacs title="~/.config/doom/config.el"
(setq doom-theme 'doom-gruvbox)
```

## Font

++ctrl+equals++ to increase font size, ++ctrl+minus++ to decrease fault size.

Practicalli recommends Fira Code font which is a very clear font for source code and also supports ligatures. Fira Code  is configured in [practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config){target=_blank}

![Fira Code font programming ligatures for Clojure](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojure/fira-code-font-clojure-ligatures.png)

```emacs title="~/.config/doom/config.el"
(setq doom-font (font-spec :family "Fira Code" :size 14 :weight 'semi-light))
```

TODO: set font for big mode ++spc++ ++"t"++ ++"b"++

??? INFO "Doom Font variables"
    Doom exposes five (optional) variables for controlling fonts in Doom:

    - `doom-font' -- the primary font to use
    - `doom-variable-pitch-font' -- a non-monospace font (where applicable)
    - `doom-big-font' -- used for `doom-big-font-mode'; use this for presentations or streaming.
    - `doom-unicode-font' -- for unicode glyphs
    - `doom-serif-font' -- for the `fixed-pitch-serif' face

    'C-h v doom-font' for documentation and more examples of what they accept. For example:




## Automatic Whitespace removal

Is this in the autoformat module ?

``
++spc++ ++"c"++ ++"w"++ deletes whitespace at end of lines

++spc++ ++"c"++ ++W++ deletes whitespace at end of lines

