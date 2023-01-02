# snippets

Yasnippets is provided by the `snippets` module

Add snippets to the `.config/doom/snippets` directory, under a directory named after the major mode in which the snippet should be available, e.g. clojure snippets should be saved in the `.config/doom/clojure-mode/` directory.

## Creating snippets

++ctrl+"c"++ ++ctrl+"n"++ to create a new snippet in the current major mode (although that can be changed when saving the snippet)

Visually select text before creating the snippet to create a snippet from that text.

Edit the snippet using tab stops and place holders

++ctrl+"c"++ ++ctrl+"c"++ to commit the snippet, prompting for comfirmation of the major mode and if the snippet file should be saved.

!!! HINT "Creating custom yasnippets"
    A Practicalli [detailed guide to writing snippets with yasnippet](https://practical.li/blog/posts/writing-custom-snippets-for-yasnippets/) 


## Clojure LSP snippets

Enable the `lsp` and `clojure` adding lsp as an option

```emacs
lsp
(clojure +lsp)
```

Clojure LSP contains its own snippets.

[practicalli/clojure-lsp-config](https://github.com/practicalli/clojure-lsp-config) containes a range of snippets designed by Practicalli and used regularly. Add this configuration to `.config/clojure-lsp` or copy specific snippets to your clojure LSP configuration in the `:additionaal-snippets` key.

### Adding custom snippets

!!! HINT "Custom snippets for Clojure LSP"
    A Practicalli [detailed guide for writing custom snippets for Clojure LSP](https://practical.li/blog/posts/code-snippets-for-clojure-lsp/)

Edit the `config.edn` file.

The `:additional-snippets` key has a collection of hash-maps, with each hash-map representing a snippet.

`$n` represents a tab-stop, where the `TAB` key will jump throughout the snippet. `n` is an integer number to define the order of the tab-stops, e.g. `$1`, `$2`, $3.

`$0` is a special tab-stop that denotes the end of the tab-stops, ending the snippet interaction.

`${n:placeholder text}` allows text to be placed at the tab-stop to give an indication as to the value to be completed. The placeholder text is automatically highlighted when tabbing into the tab-stop, so typing a new value replaces the placeholder text.

Highlighting and replacing the text does not work for the `$0` tab-stop, so placeholder text should not be used with this specific tab-stop.
