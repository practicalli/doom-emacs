# Evil Editing

Evil provides vim-style multiple editing states, greatly increasing key binding reuse and minimising the need for simultaneous key presses.

Doom Emacs provides Evil editing states

* **normal** - for manipulating and navigating existing text (default state)
* **insert** - for writing new text
* **visual** - for selecting blocks of text

!!! HINT "Normal state by default"
    Evil normal state should be used most of the time, unless writing lots of new code or text.

## Normal state

++"j"++,++"k"++,++"h"++,++"l"++ to navigate text, use with ++ctrl++ to navigate menus, with ++spc++ ++"w"++ to navigate windows

## Insert state

Insert new text (or ++delete++), e.g. when writing new code or documentation

The most common keys to enter insert mode from normal mode are:

++"i"++ to insert before the cursor, ++"a"++ to append after the cursor

++"o"++ to insert an new line below the cursor, ++"O"++ to insert a new line after the cursor

++"f"++ ++"d"++ or ++esc++ to leave insert mode and return to normal mode.


## Visual state

Select characters, words, lines and regions with visual select.  The background changes color to visually indicate which text is selected

++"v"++ to visually select a region and run commands on the text in that region.  Selection can be done with the navigation keys or motions objects such as word `w` and locations such as end of line `$`.

++shift+"v"++ to visually select by line.  ++"v"++ ++"g"++ ++"g"++ to select from current position to top of file, ++"v"++ ++"G"++ to select from current point to end of file.

++ctrl+"v"++ to select a region using the `hjkl` navigation keys, e.g. to select table data.

++"g"++ ++"c"++ on a selected region will add comment characters to the start of each line in the region

++"v"++ ++tilde++ toggles the case of the selected text (upper/lower case)

`o` to toggle between the left and right side of selection


## Evil surround

++"S"++ to surround the current character with the given character, i.e. ++double-quotes++

++"v"++ ++s++ followed by a character will surrond the visually selected text with that character.


## Learn Vim-style editing

Vim-style editing is arguably the most effective way to work with text, supporting changes as much through text manipulation as editing text.  Once practised, vim-style editing is far faster than uni-mode editing.

The recommended way to learn vim style editing is to practice and ideally use it for everything you do.

++spc++ ++"h"++ ++t++ ++"v"++ starts the build in Vim tutorial.  This provides the basic movement of vim and provides an interactive way to practice your skills

To help make Vim style editing become a sub-conscious act you should [learn to speak Evil](../vim-style/speaking-evil.md)

[Vim Adventures](https://vim-adventures.com/){target=_blank} is a web-based game that is an alternative to practising Vim.


### Learning resource for Evil

* [Graphical Cheatsheet Tutorial](http://www.viemu.com/a_vi_vim_graphical_cheat_sheet_tutorial.html){target=_blank}
* [Vim quick reference guide](http://vimhelp.appspot.com/quickref.txt.html){target=_blank}
* [Vim Casts](http://vimcasts.org/){target=_blank}

<p style="text-align:center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/a6Q8Na575qc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>
