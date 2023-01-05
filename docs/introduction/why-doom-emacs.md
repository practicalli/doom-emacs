# Why Doom Emacs

Practicalli is evaluating Doom Emacs after many years of using Spacemacs (which is still the main Emacs configuration used)

Reasons to select doom to date:

- Experience feels closer to using Neovim, so may be more of a bridge between Emacs and Neovim (help with adoption od Conjure)
- Vertico completion seems comparible to the features regularly used in other tools (Helm, Ivy)
- Package mangager pins specific versions of packages, so potentially more stability.  Managing versions of packages seems a litle simpler in Doom, although its only a small difference
- Minimal set of features and an optomised dashboard (similar to Neovim), so perception of faster start up, although saved session needs to be restored after startup.
- Startup speed - a few seconds to start up Emacs is perfectly fine for the Practicalli workflow, where Emacs typically stays running for weeks or months


## Spacemacs or Emacs Doom Configuations

Spacemacs and Doom Emacs are both open source projects that provide a large amount of common configuration in an easy to use way (typically with little or no Emacs Lisp knowledge required).

Spacemacs includes far greater number of commands in its default install (via Emacs packages) and has far greater depth to its documentation.

Doom Emacs contains only the essentials and documentation can be quite sparse in many places, so more searching and help from the community may be required.  Additional Emacs Lisp seems to be more prevelant in Doom Emacs.

There are a nuber of common features between the two configurations:

- completion frameworks: Spacemacs uses Helm and Doom Emacs uses Vertico to achieve a common set of features (Helm has a greater number of feactures although they share common core)
- projectile project management
- Package abstraction: Spacemacs layers and Doom modules are used over individual Emacs packages
- package manager (Spacemacs: packages.el, Doom: straight.el)
- modelines and themes: Practicalli uses the same modeline and theme for Spacemacs and Doom Emacs


## Migrating from Spacemacs

Challenging areas when adopting Doom Emacs initially

1.  key bindings (mnemonic and consistent key bindings used in Spacemacs are not consistent in Doom, although [practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config) adds back many of the most common Spacemacs key bindings.
2.  minimla features by default - Doom Emacs is minimal by design although contains modules (comparable to Spacemacs layers) that are easily added to greatly increase features
3.  learning the different tools that come with Doom (vertico, multiedit, etc) - similar features are provided by different modules and therefore different Emacs packages
4.  Documentation is sparse - built-in docs are good where they have been added, although many modules are undocumented and require investigation of the underlying package documentation


## Is Doom faster than other Emacs configurations

Startup time was specifically optomised in Doom Emacs and it only opens a minimal dashboard buffer, giving an experience comparable to Neovim.  Session state is not loaded by default when starting Emacs, although there is a command on the dashboard to restore the session.

Factor in the restor of state in startup time, there is very little difference between a default install of Doom Emacs or Spacemacs.

Practicalli hasnt experienced a noticable performance difference with Doom, as the vast majority of code is in the shared packages that are used by Doom and other projects.

Any configuration that is adopted will be slow to use initially, especially if it is unfamiliar.  Before changing the key bindings I found Doom slower to use as it does not provide a full set of mnemonic key bindings I was used to and was therefore less intuitive to used compared to Spacemacs.

The [Doom Emacs Clojure module key bindings](https://github.com/hlissner/doom-emacs/blob/develop/modules/lang/clojure/README.org) have been reboud in by Practicalli to extend the commands available.

!!! QUOTE
    The slowest part of the workflow is the person operating the tool.  When interation with a tool doesnt flow smoothly, the speed of the tool becomes largely irrelevant - John Stevenson
