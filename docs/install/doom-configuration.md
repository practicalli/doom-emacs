# Doom Emacs configuration

Doom curates a large number of modules, a module being one or more Emacs packages with configuration.

`~/.config/doom/` contains three configuration files created by the install process.

* init.el - enable / disable Doom modules
* config.el - elisp configuration, setting variables, etc.
* packages.el - manage specific packages, adding to or overriding packages in the Doom modules


??? HINT "Check parens are balanced in config"
    `check-parens` command will check the current buffer for balanced parens (all open parens have a matching close paren)


## Doom modules

++spc++ ++"h"++ ++"d"++ ++"m"++ to list the built-in Doom module documentation  (NOTE: documentation for some modules can be light or non-existant)

Edit `.config/doom/init.el` to select modules to be included.

[practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config) has a curated set of modules

The most useful modules include:

| Module           | Description                                   |
|------------------|-----------------------------------------------|
| (clojure +lsp)   | Cider and Clojure Mode                        |
| lsp              | language server support UI                    |
| (magit +forge)   | Rich Git Client with Forge Issue & PR support |
| (docker +lsp)    | editing in many places at once                |
| multiple-cursors | editing in many places at once                |


## Personal information

```emacs
(setq auth-sources '("~/.authinfo.gpg")
      auth-source-cache-expiry nil) ; default is 7200 (2h)
```

## buffers

Set new buffers to open in org-mode rather than fundamntal-mode

```emacs
(setq-default major-mode 'org-mode)
```


## Line Numbers

`display-line-numbers-type` defines the type of line numbers.

- `nil` consecutive line numbering, 1,2,3,...
- `relative` relative numbers to current line for vim navigation, e.g. `24 j` to jump down 24 lines.

Set to relative for Vim-style relative numbers, to support jumping lines, e.g. ++2++ ++4++ ++j++

```emacs title="~/.config/doom/config.el"
(setq display-line-numbers-type 'relative)
```

## Frames

++spc++ ++"t"++ ++f++ toggles the current frame to be full screen

Configure Emacs to always start maximized

```emacs title="~/.config/doom/config.el"
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


## Treemacs

Preview files when navigating file names in treemacs

> Not used by practicalli/doom-emacs-config

```emacs title=".config/doom/config.el"
;; Not currently used in practicalli/doom-emacs-config
(map! :map treemacs-mode-map
      "<down>" (lambda (&optional arg) (interactive)
                 (next-line arg)
                 (save-selected-window
                   (treemacs-RET-action)))
      "<up>" (lambda (&optional arg) (interactive)
               (previous-line arg)
               (save-selected-window
                 (treemacs-RET-action))))
```


## Version control

Magit Forge will use encrypted developer tokens stored in authinfo.gpg to access GitHub / GitLab API, to manage issues and pull requests.

```emacs
(setq auth-sources (list
                    (concat (getenv "XDG_CONFIG_HOME") "/authinfo.gpg")
                    "~/.authinfo.gpg"))
```


## Format tools

Markdown

++spc++ ++colon++ `+format/buffer`

```shell
sudo npm install markdownlint
```


### Indent

TAB with cursor at start of a line will indent the line, any other position on the line it will try to insert a tab

Configure TAB to always indent the line, no matter the column position

```emacs
(setq tab-always-indent 'complete)
```


### Whitespace cleanup

++spc++ ++"c"++ ++"w"++ deletes whitespace at end of lines

++spc++ ++"c"++ ++W++ deletes whitespace at end of lines

Automating whitespace cleanup seems very limited and requires external format tools which may also use a number of format rules that may or may not be of value.

??? WARNING "Format module requires format tools"
    Doom does not have the capability to remove whitespace by itself

    Enable the `format` module with the `+onsave` option to call the respective format tool

    ```emacs title=".config/doom/init.el"
    (format +onsave)
    ```

Install the format Command Line tools

- Prettier - Markdown and others...

```shell
sudo npm install --global prettier
```

??? WARNING "Prettier has very limited Markdown rule configuration"
    Prettier only has one configuration option, whether to wrap lines.  It is not possible to configure any rules as with MarkdownLint.



## Docker support

`(docker +lsp)` for Docker module with LSP support, providing Dockerfile lint and syntax support

LSP server binary provided by `dockerfile-language-server-nodejs` package

```shell
sudo npm install --global dockerfile-language-server-nodejs
```

This module assumes `docker`, `docker-compose` and =docker-machine= binaries are installed and accessible from your PATH.


## Performance tweaks

Configuration files for doom start with lexical binding which has performance advantages.

```emacs title=".config/doom/+clojure.el"
;;; +clojure.el -*- lexical-binding: t; -*-
```

* [Performance advantages of lexical scope](https://nullprogram.com/blog/2016/12/22/)
