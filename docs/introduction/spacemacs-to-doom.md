# Migrate from Spacemacs to Doom Emacs

The major differences between Spacemacs and Doom Emacs

* Key bindings
* Completion framework (vertico rather than helm)
* Spacemacs added touches (Doom has a minimal approach)


## Key bindings

[practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config){target=_blank .md-button}

[practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config){target=_blank} changes many Doom Emacs key bindings to Spacemacs bindings to easy usability of Doom Emacs.  The more familiar the key binding experience, the simpler it is to adopt Doom Emacs.

Not all key bindings have been changed and some of the Doom Emacs defaults are adopted (either because they feel easy to adopt or it is not clear how to change them effectively)

### Major changes

The [+bindings.el configuration file](https://github.com/practicalli/doom-emacs-config/blob/main/%2Bbindings.el) makes changes to the general use of Doom Emacs

++comma++ is mapped as the local leader, ++spc++ remains the leader key (common to both Doom and Spacemacs)

++spc++ ++tab++ bound to toggle to last buffer

++spc++ ++"l"++ replaces ++spc++ ++tab++ as the workspace menu, ++spc++ ++"l"++ ++tab++ added to toggle to last workspace

++spc++ ++"b"++ ++"h"++ added to jump to home buffer

++spc++ ++spc++ used as ++meta+"x"++ although the default ++spc++ ++colon++ Doom Emacs binding is kept

### File diff

`SPC D` is the Spacemacs diff menu

Doom has no menu for diff that I can find, although there are a few Emacs key bindings

`SPC d` menu provides key bindings for diff, ediff, ediff3, vc-root-diff and vc-diff.  Menu included in [practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config){target=_blank}


### Magit Status

++spc++ ++"g"++ ++"s"++ remaped to Magit Status buffer, although Doom default binding ++spc++ ++"g"++ ++"s"++ is kept

Doom bindings that are different to Spacemacs and have not been changed in [practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config){target=_blank}

`ZZ` to close and commit message and create a commit (Spaceamcs `,,`)

`ZQ` to cancel the commit message (Spaceamcs `,k`)


## Spacemacs added touches

Things added in Spacemacs not available (or not the same) in Doom Emacs


### Visual select

Spacemacs:

`SPC v` to select and additional `v` to grow selection, `V` to shrink selection

Doom:
Use `o` to toggle between ends of selection and grow using vim motions

> TODO: discover other options and identify if there is a similar approach to Spacemacs `SPC v`


## Paste

Spacemacs:

`p` shows the paste transient state menu, allowing for cycling the kill ring and pasting different values


Doom:
`p M-y` will paste the current value and use yank-pop to cycle through the kill ring

`SPC i y` inserts a value from the kill ring, showing a popup list of the history


## Whitespace clean up

Spacemacs can be configured to automattically remove extra whitespace when saving a file.

Doom: ++spc++ ++"c"++ ++"w"++ key binding removes extra whitespace

> TODO: automate whitespace removal on file save
