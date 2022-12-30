# Clojure configuration

Enable the Clojure module with LSP support in the `~/.config/doom/init.el` configuration file

```emacs
(clojure +lsp)
lsp
```

Use the doom command to load the modules

```shell
doom sync
```

!!! Hint "Restart Doom Emacs after larger changes"
    ++spc++ ++"q"++ ++"r"++ to restart Doom Emacs when significant changes are made or something is not working correctly


## Clojure CLI

[Practicalli Clojure install guide](https://practical.li/clojure/clojure-cli/install/){target=_blank .md-button}

[Clojure CLI](https://clojure.org/guides/deps_and_cli){target=_blank} provides a way to run Clojure code, packaged Clojure (jar) and of course run a Clojure REPL.

[Practicalli Clojure install guide](https://practical.li/clojure/clojure-cli/install/){target=_blank} details prerequisites, Clojure install options and supporting tools for an enhanced developer workflow.  Or visit the [Clojure Getting Started guide](https://clojure.org/guides/getting_started){target=_blank} for just the Clojure CLI.

[practicalli/clojure-deps-edn provides a wide range of community tools](https://practical.li/clojure/clojure-cli/install/community-tools.html){target=_blank} that can easily be added to the development environment and used across all projects.

!!! WARNING "Aliases are required for many command examples"
    Without [installing practicalli/clojure-deps-edn](https://practical.li/clojure/clojure-cli/install/community-tools.html){target=_blank} many commands provided in this book will not work, unless the same alias configuration is added to a either a project or user level `deps.edn` configuration.


## Clojure LSP

[Clojure LSP installation guide](https://clojure-lsp.io/){target=_blank .md-button } 
[Practicalli Clojure LSP configuration](http://github.com/practicalli/clojure-lsp-config){target=_blank .md-button}

![Clojure Language Server Protocol LSP](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojure/clojure-language-server.png)

Clojure LSP provides a [standard set of features](https://emacs-lsp.github.io/lsp-mode/){target=_blank} for editing and manipulating source code, e.g. autocompletion, code navigation, refactor code, inline syntax errors and idiom warnings.

!!! INFO "LSP and the REPL"
    The REPL is used to design Clojure effectively by providing instant feedback on code expressions as they are written and evaluated.  A REPL based workflow supports the most effective approach to development of Clojure apps and services.
    Clojure LSP supports the editing activities to write Clojure code effectively, providing a static analysis of the code base that drives advance editing, navigation and refactor tasks.

[Install the Clojure LSP command line tool](https://clojure-lsp.io/){target=_blank} and configure `~./config/clojure-lsp/config.edn` or use [Practicalli Clojure LSP configuration](http://github.com/practicalli/clojure-lsp-config){target=_blank} which provides a complete configuration for clojure-lsp (`config.edn`), including a wide range of snippets and less restrictive formatting rules (`cljfmt.edn`).


=== "Free Desktop XDG Config"

    Clone via SSH
    ```shell
    git clone -o practicalli git@github.com:practicalli/clojure-lsp-config.git $XDG_CONFIG_HOME/clojure-lsp
    ```

    Clone via HTTPS
    ```shell
    git clone -o practicalli https://github.com/practicalli/clojure-lsp-config.git $XDG_CONFIG_HOME/clojure-lsp
    ```

=== "Classic Config"
    Clone via SSH
    ```shell
    git clone -o practicalli git@github.com:practicalli/clojure-lsp-config.git $HOME/.clojure-lsp
    ```

    Clone via HTTPS
    ```shell
    git clone -o practicalli https://github.com/practicalli/clojure-lsp-config.git $HOME/.clojure-lsp
    ```

Run the clojure-lsp command in a terminal to ensure the install was successful.

```shell
clojure-lsp -v
```

??? INFO "Clojure LSP and clj-kondo"
    Clojure LSP includes clj-kondo to provide [an implementation of the Language Server Protocol for the Clojure Language](https://clojure-lsp.io/){target=_blank}. clj-kondo provides static analysis of source code files, providing subtle warnings as Clojure code is written to help the developer follow idioms and avoid syntatic errors.



## References

* [Configure Emacs as a Clojure IDE guide](https://emacs-lsp.github.io/lsp-mode/tutorials/clojure-guide/)
* [A guide on disabling/enabling lsp-mode features](https://emacs-lsp.github.io/lsp-mode/tutorials/how-to-turn-off/)
* [Emacs LSP UI website](https://emacs-lsp.github.io/lsp-ui/) and [emacs-lsp/lsp-ui repository](https://github.com/emacs-lsp/lsp-ui)
