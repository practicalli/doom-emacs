# Spacemacs or Emacs Doom

Spacemacs and Doom Emacs are both open source projects that provide a large amount of common configuration in an easy to use way (typically with little or no Emacs Lisp knowledge required).

## Common features

- helm or ivy - both completion frameworks availalable (defaults: Spacemacs uses Helm, Doom uses Ivy)
- projectile project management
- layers rather than individual packages
- package manager (Spacemacs: packages.el, Doom: straight.el)
- modelines, themes and anything else you can think of probably



## Is Doom faster than other Emacs configurations

The most noticable difference between Doom and other Emacs configurations is that Doom uses Ivy by default, which typically uses less resources than Helm, as Ivy does not have the comprehensive level of features that Helm provides.

Otherwise Practicalli hasnt experienced a noticable performance difference with Doom, as the vast majority of code is in the shared packages that are used by Doom and other projects.

Emacs packages do most of the work, so try a different package (e.g. Ivy instead of Helm).  Doom, Spacemacs and Prelude are all running on Emacs, so if you find something is running slow, try a different packaging of Emacs for your operating system and make sure you are on Emacs 27.1 or greater.

Doom Emacs has very few features enabled by default, so the startup time after install is initially very fast (of little importance if you have Emacs open for weeks or running as a server / deamon).

Personally I find Doom slower to use as it does not provide a full set of mnemonic key bindings and are therefore less intuitive to used compared to Spacemacs.  See the [Clojure module key bindings](https://github.com/hlissner/doom-emacs/blob/develop/modules/lang/clojure/README.org) for example.  This could be fixed by re-binding most of the default key bindings to be mnemonic in your own personal configuration.

In the end the slowest part of the equation is the person operating Emacs.  If you are slow to tell Emacs what to do, it doesnt matter how fast it does it...
