# Completion with Vertico

Vertico module enhances the Emacs search and completion experience, with united interface for project search and replace, powered by [ripgrep](https://github.com/BurntSushi/ripgrep/)

The primary packages are:

- Vertico - vertical completion user interface
- Consult - suite of useful commands using ~completing-read~
- Embark - set of minibuffer actions
- Marginalia - annotations to completion candidates
- Orderless - additional filtering methods

Consult can use several external tools which must be installed to use their features

- [fzf](https://github.com/junegunn/fzf) 
- [Dash docsets](https://kapeli.com/dash) 
- [pass](https://www.passwordstore.org/) 


## Module flags
- +childframe
  Display completion candidates in a [child frame](https://www.gnu.org/software/emacs/manual/html_node/elisp/Child-Frames.html) rather than an overlay or tooltip. *Requires GUI Emacs.*

- +icons ::
  Add icons to =file= and =buffer= category completion selections.


## Vertico keybindings

When in an active Vertico completion session, the following doom added keybindings are available:

| Keybind                                | Description                                                    |
|----------------------------------------|----------------------------------------------------------------|
| ++ctrl+"k"++                           | (evil) Go to previous candidate                                |
| ++ctrl+"j"++                           | (evil) Go to next candidate                                    |
| ++ctrl+meta+"k"++                      | (evil) Go to previous group                                    |
| ++ctrl+meta+"j"++                      | (evil) Go to next group                                        |
| ++ctrl+semi-colon++ or ++spc++ ++"a"++ | Open an ~embark-act~ menu to chose a useful action             |
| ++ctrl+"c"++ ++ctrl+semi-colon++       | export the current candidate list to a buffer                  |
| ++ctrl+"c"++ ++ctrl+"l"++              | ~embark-collect~ the current candidate list (collect verbatim) |
| ++ctrl+spc++                           | Preview the current candidate                                  |

`embark-act` will prompt you with a =which-key= menu with useful commands on the selected candidate or candidate list, depending on the completion category.

!!! HINT "Marginalia annotaions on help menu"
    ++ctrl+"h"++ shows a help menu of options with a Vertico buffer showing more detailed descriptions from Marginalia annotations


## Jump-to navigation

Navigate within a project using projectile

https://assets.doomemacs.org/completion/vertico/projectile.png

| Keybind                 | Description                         |
|-------------------------|-------------------------------------|
| ++spc++ ++"p"++ ++"f"++ | Jump to file in project             |
| ++spc++ ++"f"++ ++"f"++ | Jump to file from current directory |
| ++spc++ ++"s"++ ++"i"++ | Jump to symbol in file              |



## Project search & replace

This module provides interactive text search and replace using ripgrep.

| Keybind                 | Description              |
|-------------------------|--------------------------|
| ++spc++ ++"s"++ ++"p"++ | Search project           |
| ++spc++ ++"s"++ ++"P"++ | Search another project   |
| ++spc++ ++"s"++ ++"d"++ | Search this directory    |
| ++spc++ ++"s"++ ++"D"++ | Search another directory |

https://assets.doomemacs.org/completion/vertico/search.png

++spc++ ++"u"++ universal argument prefix to commands instructs the search tool to include ignored file patterns.

++ctrl+c+ctrl+"e"++ to send the search results to an editable buffer


++"Z"++ ++"Z"++ or ++ctrl+c+ctrl+"c"++ to commit changes

++"Z"++ ++"Q"++ or ++ctrl+c+ctrl+"k"++ to abort changes

https://assets.doomemacs.org/completion/vertico/search-replace.png


## In-buffer searching

This module provides some in buffer searching bindings:

- [[kbd:][spc s s]] (~isearch~)
- [[kbd:][spc s S]] (~+vertico/search-symbol-at-point~ via ~consult-line~)
- [[kbd:][spc s b]] (~consult-line~)

https://assets.doomemacs.org/completion/vertico/buffer-search.png

An ~occur-edit~ buffer can be opened from ~consult-line~ with [[kbd:][C-c C-e]].

## Vertico integration

| Keybind                              | Description                   |
| ------------                         | ----------------------------- |
| ++"M"++ ++"x"++ or ++spc++ ++colon++ | Enhanced M-x                  |
| ++spc++ ++quote++                    | Resume last Vertico session   |


### Jump to files, buffers or projects

| Keybind                                            | Description                             |
| ------------------                                 | --------------------------------------- |
| ++spc++ ++enter++                                  | Find bookmark                           |
| ++spc++ ++"f"++ ++"f"++ or ++spc++ ++period++      | Browse from current directory           |
| ++spc++ ++"p"++ ++"f"++ or ++spc++ ++spc++         | Find file in project                    |
| ++spc++ ++"f"++ ++"f"++                            | Find recently opened file               |
| ++spc++ ++"p"++ ++"f"++                            | Open another project                    |
| ++spc++ ++"b"++ ++"b"++ or ++spc++ ++comma++       | Switch to buffer in current workspace   |
| ++spc++ ++"b"++ ++"B"++ or   ++spc++ ++less-than++ | Switch to buffer                        |

[[kbd:][spc b b]] and [[kbd:][spc ,]] support changing the workspace you're selecting a buffer from
via [[https://github.com/minad/consult#narrowing-and-grouping][Consult narrowing]], e.g. if you're on the first workspace, you can switch to
selecting a buffer from the third workspace by typing [[kbd:][3 spc]] into the prompt, or
the last workspace by typing [[kbd:][0 spc]].

[[kbd:][spc f f]] and [[kbd:][spc .]] support exporting to a [[kbd:][wdired]] buffer using [[kbd:][C-c C-e]].

## Search
| Keybind | Description                               |
|---------+-------------------------------------------|
| [[kbd:][spc p t]] | List all TODO/FIXMEs in project           |
| [[kbd:][spc s b]] | Search the current buffer                 |
| [[kbd:][spc s d]] | Search this directory                     |
| [[kbd:][spc s D]] | Search another directory                  |
| [[kbd:][spc s i]] | Search for symbol in current buffer       |
| [[kbd:][spc s p]] | Search project                            |
| [[kbd:][spc s P]] | Search another project                    |
| [[kbd:][spc s s]] | Search the current buffer (incrementally) |

##* File Path Completion
Note that Emacs allows you to switch directories with shadow paths, for example
starting at =/foo/bar/baz=, typing =/foo/bar/baz/~/= will switch the searched
path to the home directory. For more information see ~substitute-in-file-name~
and ~file-name-shadow-mode~. This module will erase the "shadowed" portion of
the path from the minibuffer, so in the previous example the path will be reset
to =~/=.

## Consult

* Multiple candidate search
This module modifies the default keybindings used in
~consult-completing-read-multiple~:
| Keybind | Description                                                 |
|---------+-------------------------------------------------------------|
| [[kbd:][TAB]]     | Select or deselect current candidate                        |
| [[kbd:][RET]]     | Enters selected candidates (also toggles current candidate) |

##* Async search commands
:PROPERTIES:
:ID:       4ab16bf0-f9e8-4798-8632-ee7b13d2291e
:END:
Consult async commands (e.g. ~consult-ripgrep~) will have a preceding separator
character (usually ~#~) before the search input. This is known as the =perl=
splitting style. Input typed after the separator will be fed to the async
command until you type a second seperator, afterwhich the candidate list will be
filtered with Emacs instead (and can be filtered using [[doom-package:orderless]], for example).
The specific seperator character can be changed by editing it, and might be
different if the initial input already contains =#=.

Note that grep-like async commands translate the input (between the first and
second =#=) to an Orderless-light expression: space separated inputs are all
matched in any order. If the grep backend does not support PCRE lookahead, it'll
only accept 3 space separated inputs to prevent long lookup times, and further
filtering should be done after a second =#=.

For more information [[https://github.com/minad/consult#asynchronous-search][see here]].

## Marginalia

| Keybind | Description                     |
|---------+---------------------------------|
| [[kbd:][M-A]]     | Cycle between annotation levels |

Marginalia annotations for symbols (e.g. [[kbd:][spc h f]] and [[kbd:][spc h v]]) come with extra
information the nature of the symbol. For the meaning of the annotations see
~marginalia--symbol-class~.

## Orderless filtering
When using orderless to filter through candidates, the default behaviour is for
each space separated input to match the candidate as a regular expression or
literally.

Note that due to this style of matching, pressing tab does not expand the input
to the longest matching prefix (like shell completion), but rather uses the
first matched candidate as input. Filtering further is instead achieved by
pressing space and entering another input. In essence, when trying to match
=foobar.org=, instead of option 1., use option 2.:

1. (BAD) Enter ~foo TAB~, completes to =foobar.=, enter ~org RET~
2. (GOOD) Enter ~foo spc org RET~

Doom has some builtin [[https://github.com/oantolin/orderless#style-dispatchers][style dispatchers]] for more fine-grained filtering, which
you can use to further specify each space separated input in the following ways:
| Input        | Description                              |
|--------------+------------------------------------------|
| ~!foo~         | match without literal input =foo=          |
| ~%foo~ or ~foo%~ | perform ~char-fold-to-regexp~ on input =foo= |
| ~`foo~ or ~foo`~ | match input =foo= as an initialism         |
| ~=foo~ or ~foo=~ | match only with literal input =foo=        |
| ~~foo~ or ~foo~~ | match input =foo= with fuzzy/flex matching |
