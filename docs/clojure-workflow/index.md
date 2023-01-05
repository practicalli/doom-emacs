# Clojure Developmement Workflow

??? INFO "Aliases used in examples are defined in practicalli/clojure-deps-edn"
    [practicalli/clojure-deps-edn](https://github.com/practicalli/clojure-deps-edn) contains a wide range of aliases and community tools for Clojure CLI projects.

    `:env/dev` adds `dev` directory to the class path, used to load `dev/user.clj` file and run development tools on REPL startup

    `:env/test` adds `test` directory to include unit tests and common testing libraries

    `:repl/rebel` runs a rich terminal UI and an nREPL server to allow connection from [Clojure aware editors](https://practical.li/clojure/clojure-editors/)


## Start Clojure REPL

=== "Command Line"

    Start a REPL in a terminal window with a rich REPL UI prompt, with auto-completion, syntax highlighting, multi-line editing and documentation.
    ```shell
    clojure -M:env/dev:env/test:repl/rebel
    ```

    Or start a headless REPL if only using the REPL via the editor
    ```shell
    clojure -M:env/dev:env/test:repl/headless
    ```

    ++comma++ ++"c"++ to connect to an existing Clojure REPL and follow the prompts to connect to `localhost`


=== "Doom Emacs"
    Doom Emacs can launch a REPL process and connect to that process without leaving Emacs. External tools (Clojure CLI, Leiningen) are used to actually start the REPL process and CIDER manages the connection and communication with the REPL process from within Doom Emacs.

    ++comma++ ++single-quote++ to start a Clojure REPL using `cider-jack-in`

    Include a `.dir-locals.el` file in the root of the Clojure project to include Clojure CLI aliases
    ```elisp
    ((clojure-mode . ((cider-preferred-build-tool . clojure-cli)
                  (cider-clojure-cli-aliases . ":env/dev:env/test"))))
    ```


## Evaluate code

++comma++ ++"e"++ opens the evaluation menu


## Snippets

Snippets from Yasnippets appear when typing matches the name of the snippet defined in the major mode.

Clojure also has snippets defined from Clojure LSP.

