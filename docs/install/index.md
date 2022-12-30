# Install Spacemacs

[Install prerequisites: Emacs, Java 17, Clojure CLI and Command Line tools ](pre-install.md){.md-button}

1. [Clone Doom Emacs](#clojure-doom-emacs) to `~/.config/emacs`
2. [Clone practicalli/doom-emacs-config configuration](#clone-practicalli-doom-emacs-configuration) to add common layers for Clojure development.  Or start Emacs and use the Spacemacs install wizard for basic config, follow the [manual configuration section](manual-configuration/) for additional features.
3. [optional] [Install Fira Code font](#install-fira-code-font) (change `dotspacemacs-default-font` to a name of a font on your operating system in `.spacemacs.d/init.el` in step 4)
4. [Install All The Icons fonts for doom modeline theme](#all-the-icon-fonts)


## Clone Doom Emacs

Use your favourite git client or the following command in a terminal window to clone Spacemacs and then run the Doom Emacs install script

??? HINT "Use Practicalli Doom Emacs config rather than install"

=== "Free Desktop XDG config"
    ```
    git clone https://github.com/hlissner/doom-emacs ~/.config/emacs

    ~/.config/emacs/bin/doom install
    ```

    `~/.config/doom` directory will be created by the install and contain the default configuration.


=== "Classic config"
    ```
    git clone https://github.com/hlissner/doom-emacs ~/.emacs.d

    ~/.emacs.d/bin/doom install
    ```

## Post install

Doom Emacs outputs the following message at the end of the install

1. Don't forget to run 'doom sync', then restart Emacs, after modifying
   ~/.doom.d/init.el or ~/.doom.d/packages.el.

   This command ensures needed packages are installed, orphaned packages are
   removed, and your autoloads/cache files are up to date. When in doubt, run
   'doom sync'!

2. If something goes wrong, run `doom doctor`. It diagnoses common issues with
   your environment and setup, and may offer clues about what is wrong.

3. Use 'doom upgrade' to update Doom. Doing it any other way will require
   additional steps. Run 'doom help upgrade' to understand those extra steps.

4. Access Doom's documentation from within Emacs via 'SPC h d h' or 'C-h d h'
   (or 'M-x doom/help')


## Add Doom command to path

Add `.config/emacs/bin` to 

Or create a symbolic link

```shell
cd .local/bin
ln -s ~/.config/emacs/bin/doom doom
```


## Run Emacs 

The packages have been downloaded as part of the Doom Emacs install process.

Run emacs from a desktop launcher or on the command line:
```shell
emacs
```
!!! WARNING "Native compliation initial high cpu use"
    On first running Emacs after Doom install added packages, the elisp code will be compiled to native binaries.  The compilation will use a lot of CPU resources


##  Clone Practicalli Doom configuration

!!! WARNING "Not started yet"

Clone [practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config) or first create a fork and clone that fork


=== "Free Desktop XDG config"
    Using SSH
    ```shell
    git clone git@github.com:practicalli/doom-emacs-config.git ~/.config/doom
    ```


    Using HTTPS
    ```shell
    git clone https://github.com/practicalli/doom-emacs-config ~/.config/doom
    ```

=== "Classic config"
    Using SSH
    ```shell
    git clone git@github.com:practicalli/doom-emacs-config.git ~/.config/doom
    ```

    Using HTTP
    ```shell
    git clone https://github.com/practicalli/doom-emacs-config ~/.config/doom
    ```

    `~/.spacemacs.d/init.el` is the main configuration file, ensure `~/.spacemacs` file does not exist as that file would take precedence.


??? INFO "Emacs custom settings"
    `.spacemacs.d/init.el` configuration separates Emacs custom settings into a `emacs-custom-setting` file.  `emacs-custom-setting` should be added to version control if the Emacs `customize` menu has been used to define settings.
    `emacs-custom-file` is defined in the `dotspacemacs/user-init` of the Spacemacs configuration
    ```elisp
      (setq custom-file (file-truename (concat dotspacemacs-directory "emacs-custom-settings.el")))
      (load custom-file)
    ```
    A specific path could also be used to define the location of the custom file: `(setq custom-file "~/.emacs.d/.cache/custom-settings")`


## Install Fira Code font

[Install Fira Code](https://github.com/tonsky/FiraCode/wiki/Installing){target=_blank .md-button}

[practicalli/spacemacs.d](https://github.com/practicalli/spacemacs.d) uses Fira Code, a mono-spaced font designed for source code and includes [ligatures](https://github.com/tonsky/FiraCode#whats-in-the-box) and [many other features](https://github.com/tonsky/FiraCode#whats-in-the-box).

![Fira Code font - ligatures for Emacs and Clojure code](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojure/fira-code-font-clojure-ligatures.png)

!!! TIP "Use a different font with practicalli/spacemacs.d"
    To use a different font when using the [practicalli/spacemacs.d](https://github.com/practicalli/spacemacs.d), edit `.spacemacs.d/init.el` and update the value for `dotspacemacs-default-font` to a name of a font on your system.



## All The Icon Fonts

[practicalli/spacemacs.d](https://github.com/practicalli/spacemacs.d){target=_blank} configuration uses the modern looking doom modeline theme, which requires a few fonts and icons.

`SPC SPC all-the-icons-install-fonts` once Spacemacs is running will install the fonts.

++spc++ ++"q"++ ++"r"++ to restart Spacemacs and see the finished results

![Spacemacs - doom-gruvbox-light theme - home and spacemacs config buffers](https://raw.githubusercontent.com/practicalli/graphic-design/live/spacemacs/screenshots/spacemacs-doom-gruvbox-light-theme-examples-home-spacemacs-config.png)


## Spacemacs is ready for action

Spacemacs is now up and running and ready to take on the world.

If you already know how to use Spacemacs, jump to the [Clojure Projects section](/spacemacs/clojure-projects/), otherwise look through the [Spacemacs Basics section](/spacemacs/spacemacs-basics/) to learn how to use Vim style editing and work with files, buffers and windows in Spacemacs.
