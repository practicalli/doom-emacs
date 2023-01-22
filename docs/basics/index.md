# Basic usage

[Projects](projects.md){.md-button}
[Workspaces](workspaces.md){.md-button}
[Evil Tools](evil-tools.md){.md-button}


## Command Menu

++spc++ is the leader key that opens the main Doom Emacs command menu

++comma++ is the localleader key that opens a context specific menu, with commands for the current major mode (clojure, markdown, yaml, etc.)


## Line numbers

++spc++ ++"t"++ ++"l"++ toggles consecutive line numbers


## Theme

++spc++ ++"h"++ ++"t"++ lists the theme names available, select a theme name to change the theme instantly.

!!! NOTE "Confirm Theme should run elisp code"
    Doom prompts to confirm if elisp should be run if included in a theme.  A theme can be marked as safe, so further confirmation is not required.


## Zoom Frame and text

++spc++ ++"t"++ ++"b"++ to toggle Doom Big mode which applies `doom-big-font` to text across all buffers, essentailly scaling the Emacs frame.

Leaving Doom Big mode resets the text size to `doom-font`.  This is the recommended approach to scaling Doom Emacs.

??? INFO "Set Doom font sizes in config.el"
    Set a standard size font for general use and a big font for demos, screencasts, pairing, etc.  The following configuration is used in [practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config){target=_blank}

    ```emacs title="~/.config/doom/config.el"
    ;; See 'C-h v doom-font' for documentation and more examples of what they accept. For example:
    ;;(setq doom-font (font-spec :family "Fira Code" :size 12 :weight 'semi-light)
    ;;      doom-variable-pitch-font (font-spec :family "Fira Sans" :size 13))

    (setq doom-font (font-spec :family "Fira Code" :size 14)
          doom-big-font (font-spec :family "Fira Code" :size 24)
          doom-variable-pitch-font (font-spec :family "Ubuntu" :size 16))
    ```

Alternatively the text in a specific buffer can be scalled, although this does not scale the mini-buffer and its affects are not applied to any other buffer.

++ctrl+"x"++ ++ctrl+plus++ to increase the size of text in the current buffer

++ctrl+"x"++ ++ctrl+minus++ to decrease the size of text in the current buffer

++ctrl+"x"++ ++ctrl+0++ to reest the size of text in the current buffer to the default `doom-font` size


## Files

++spc++ ++"f"++ ++"f"++ to list files in current directory or create relative files and directories

++spc++ ++"p"++ ++"f"++ to list files in current project, providing a quick way to open any file in the project by filtering the list

!!! HINT "Create files and directories"
    ++spc++ ++"f"++ ++"f"++ and typing a path and file will create the file and intermediate directories if they do not exist


## Format tools

++comma++ ++double-quote++ is typically the default format menu if available for a language major mode, calling tools specific to each language.

Automatic formatting whilst typing is supported when a language module includes the `+lsp` feature and a suitable LSP language server has been installed.

[LSP Language Server install](/doom-emacs/install/#language-servers){ .md-button }

??? INFO "Doom format module to be redeveloped"
    LSP language servers are the most effective way to support formatting in Doom Emacs, as the Doom Emacs Format module is to be rewritten.


## Whitespace cleanup

++spc++ ++"c"++ ++"w"++ to remove whitespace from end of lines and additional blank lines from the end of the file.

> NOTE: automating white space clean up may require external format or LSP tooling


## references

* [Keybind reference sheet](https://discourse.doomemacs.org/t/keybind-reference-sheet/49) - doom discourse
* [Doom Getting Started Guide](https://github.com/doomemacs/doomemacs/blob/master/docs/getting_started.org)
