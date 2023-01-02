# Practicalli Doom Emacs

Practicalli Doom Emacs is a guide to Clojure REPL Driven Development with Doom Emacs configuration and Practicalli customization.

Doom is not aimed at Emacs beginners (unless the aim is to learn Emacs in more depth).  There is limited official documentation, although there is a healthy community support. 

??? INFO "Looking for a batteries included approach?"
    [Practicalli Spacemacs](https://practical.li/spacemacs) and [practicalli/spacemacs.d](https://github.com/practicalli/spacemacs.d) provide all the Emacs features needed for Clojure, with just two Git clone commands.  Spacemacs is a community configuration for Emacs with a very large community and very detailed documentation. 

??? WARNING "New Book - content published as learned"
    Practicalli Doom Emacs was started in December 2022 with little knowledge of Doom Emacs, so is mostly a journal of things that have been learned as Practicalli tries to create an effective development workflow, especially with Clojure.  Content will be added as new things are discovered to aid in the learning and effective use of Doom Emacs.


## Practicalli Doom Emacs configuration

[practicalli/doom-emacs-config repository](https://github.com/practicalli/doom-emacs-config){target=_blank} contains a customised configuration for Clojure development and supporting tools. [Browse the repository online](https://github.com/practicalli/doom-emacs-config){target=_blank} or fork / clone the repository

=== "Free Desktop XDG Config"
    ```bash
    git clone https://github.com/practicalli/doom-emacs-config.git $XDG_CONFIG_HOME/doom`
    ```
    The above command creates `~/.config/doom/` that contains the configuration used in Practicalli Doom Emacs book, all in one place.

=== "Classic Config"
    ```bash
    git clone https://github.com/practicalli/doom-emacs-config.git $HOME/.doom.d`
    ```
    The above command creates the `~/.doom.d/` directory that contains the configuration used in Practicalli Doom Emacs book, all in one place.


![Emacs Doom](https://raw.githubusercontent.com/hlissner/doom-emacs/screenshots/main.png)


## REPL Driven Development

[![Clojure repl driven development using Clojure aware editor](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojure/clojure-repl-driven-development-lifecycle-concept.png)](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojure/clojure-repl-driven-development-lifecycle-concept.png)

The REPL is the [Clojure interactive environment](introduction/repl-workflow.md) used to create an run all code.  You will quickly get a feel for Clojure by evaluating, breaking, fixing and extending code in the REPL, all the while getting instant feedback on what your code is doing.

As we work through code we will discuss the concepts behind Clojure, including functional programming, "pure" functions and a stateless approach with persistent data structures, changing state safely, Java interoperability and tooling around Clojure.


## Resources

* [Practicalli Clojure](https://practical.li/clojure) for a practical introduction learning Clojure and provides [practicalli/clojure-deps-edn configuration](https://github.com/practialli/clojure-deps-edn) to add community tools and common aliases to Clojure CLI.
* [Practicalli YouTube channel](https://youtube.com/practicalli) - 100+ hours of Clojure related videos
* [Practicalli website](https://practical.li/) blog, books and videos to support your journey into Clojure


## Discussions and feedback

[Contributions are welcome via GitHub issues and pull requests](introduction/contributing.md), or discuss the book on the Clojurians Slack community.

[![Join the conversation on Clojurians Slack](images/practicalli-slack-channel.png)](https://clojurians.slack.com/messages/practicalli)

Get a [free Clojurians slack community account](https://clojurians.net/)


## Sponsor my work

[![Sponsor practicalli-john](https://raw.githubusercontent.com/practicalli/graphic-design/live/buttons/practicalli-github-sponsors-button.png){ align=left loading=lazy }](https://github.com/sponsors/practicalli-john/)

The majority of my work is now focused on the [Practicalli series of books and videos](https://practical.li/){target=_blank} and an advisory role with several communities

Thank you to [Cognitect](https://www.cognitect.com/){target=_blank}, [Nubank](https://nubank.com.br/){target=_blank} and a wide range of other [sponsors](https://github.com/sponsors/practicalli-john#sponsors){target=_blank} from the Clojure community for your continued support


## Creative commons license

<div style="width:95%; margin:auto;">
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a>
This work is licensed under a Creative Commons Attribution 4.0 ShareAlike License (including images & stylesheets).
</div>
