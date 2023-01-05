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



## Files

++spc++ ++"f"++ ++"f"++ to list files in current directory or create relative files and directories

> add a space to the end of the name to ensure Emacs creates a new file rather than selecting the existing name... TODO: is this to be expected

++spc++ ++"p"++ ++"f"++ to list files in current project, providing a quick way to open any file in the project by filtering the list



## Format tools

!!! INFO "Use LSP formatting where supported"
    The Doom Emacs Format module is to be rewritten as it curr so using LSP servers for languages that support them should avoid rely on LSP server implementations to format code where possible.  Doom Emacs requires external code formatting tools to be installed.

Install markdownlint package for local format tool, although this tool is not used by Doom Emacs (as far as I can tell)

```shell
sudo npm install markdownlint
```

Prettier.io was evaluated but does not allow for customisation of the linting rules, so was not adopted.


## Whitespace cleanup

++spc++ ++"c"++ ++"w"++ to remove whitespace from end of lines and additional blank lines from the end of the file.

> NOTE: automating white space clean up may require external format or LSP tooling


## references

* [Keybind reference sheet](https://discourse.doomemacs.org/t/keybind-reference-sheet/49) - doom discourse
* [Doom Getting Started Guide](https://github.com/doomemacs/doomemacs/blob/master/docs/getting_started.org)
