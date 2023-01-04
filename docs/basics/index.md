# Basic usage

## Line numbers

++spc++ ++"t"++ ++"l"++ toggles consecutive line numbers


## Spacemacs to Doom Emacs

Layouts -> workspaces

Adding a project seems to add a workspace

`SPC TAB .` to switch between workspaces


## Rename files

`SPC f f`

> add a space to the end of the name to ensure Emacs creates a new file rather than selecting the existing name... TODO: is this to be expected


## Multiple cursors

Multiple cursors is most useful where the same changes are required in multiple lines, especially where those lines may be similar in structure but not idential. Changes are made to multiple lines or places in the text where the same editing opperation is desired.

++"g"++ ++"z"++ menu for mutliple cursor menu

When changes are vertically aligined, create multiple cursors with vim-style movements:

++2++ ++4++ ++"g"++ ++"z"++ ++i++ adds a cursor to the next 24 lines

Changes in more random positions benefit from creating 'frozen' cursors in any position that only take key input once switched to mirroring or activated by Evil Insert mode

++"g"++ ++"z"++ ++"z"++ toggle new (frozen) cursors at point. Frozen cursors stay in position until mirroring switched on or switching to insert mode

++"g"++ ++"z"++ ++"t"++ toggle mirroring on and off

With visual select:

++"g"++ ++"z"++ ++i++ to create curors at start of visual selection region

++"g"++ ++"z"++ ++a++ to create curors at end (append) of visual selection region

Remove multiple cursors:

++"g"++ ++"z"++ ++"q"++ to cancel all cursors


## Format tools

NOTE: rely on LSP server implementations to format code where possible.  Doom Emacs requires external code formatting tools to be installed.

Install markdownlint package for local format tool, although this tool is not used by Doom Emacs (as far as I can tell)

#+begin_src shell
sudo npm install markdownlint
#+end_src

Prettier.io was evaluated but does not allow for customisation of the linting rules, so was not adopted.


## Whitespace cleanup

++spc++ ++"c"++ ++"w" to remove whitespace from end of lines and additional blank lines from the end of the file.

> TODO: automate white space clean up (may require external format or LSP tooling)



## references

* [Keybind reference sheet](https://discourse.doomemacs.org/t/keybind-reference-sheet/49) - doom discourse
* [Doom Getting Started Guide](https://github.com/doomemacs/doomemacs/blob/master/docs/getting_started.org)
