# Introduction

Source contend and generated static content for the Practicalli Doom Emacs book.

The Practicalli Doom Emacs provides practical guides to software development tasks, using predominantly the Clojure and ClojureScript languages.  Most of the editing techniques and tools are applicable to any editing tasks.

Doom Emacs is an open source project to provide configuration to add 150+ packages to Emacs, without having to writing a lot of common configuration code.

[![Discuss this guide on #practicalli channel of the Clojurians Slack community](images/practicalli-slack-channel.png)](https://clojurians.slack.com/messages/practicalli).

[Create a free Clojurians Slack community account](http://clojurians.net/).

This workshop will cover the following topics:
* Emacs basics, common commands and tools
* Powerful editing and refactor tools (iedt, narrowing, helm-ag, multiple cursors, visual undo)
* Adding and enhancing the Clojure layer
* Running the REPL, evaluating code, inspecting data, debug, reloaded workflow
* Running tests & test reports
* Structural editing (smartparens/evil-cleverparens)
* Clojure docs, auto-completion, snippets
* Clojurescript development, figwheel-main and reagent
* Org-mode for project documentation, literate programming & presentations


## Contributing

Issues and pull requests are most welcome.  Please detail issues as much as you can.  Pull requests are easier when they are specific to a page or at most a section.  The smaller the change the quicker it is to review and merge.

* [Kanban board of issues](https://github.com/practicalli/doom-emacs/projects/1)
* [Current Issues](https://github.com/practicalli/doom-emacs/issues)
* [Current pull requests](https://github.com/practicalli/doom-emacs/pulls)

[practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config/) GitHub repository contains the complete Spacemacs configuration used in this guide and issues and pull requests can also be made there.


## Book status

![GitHub issues](https://img.shields.io/github/issues/practicalli/doom-emacs?label=content%20ideas&logo=github)
![GitHub commit activity](https://img.shields.io/github/commit-activity/y/practicalli/doom-emacs?label=commits&logo=github)
![GitHub pull requests](https://img.shields.io/github/issues-pr-raw/practicalli/doom-emacs?label=pull%20requests&logo=github)
[![Publish Book](https://github.com/practicalli/spacemacs/actions/workflows/publish-book.yaml/badge.svg)](https://github.com/practicalli/doom-emacs/actions/workflows/publish-book.yaml)
[![MegaLinter](https://github.com/practicalli/spacemacs/actions/workflows/megalinter.yml/badge.svg)](https://github.com/practicalli/doom-emacs/actions/workflows/megalinter.yml)


## License and Contributing

<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/">
<a href="http://creativecommons.org/licenses/by-sa/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">
<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"></a>
 <a property="dct:title" rel="cc:attributionURL" href="https://github.com/practicalli/doom-emacs">Practicalli Doom Emacs</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://practical.li">Practicalli</a> is licensed under <a href="http://creativecommons.org/licenses/by-sa/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY-SA 4.0 </a></p>

Please [read the contributing section of the book](contributing.html) before raising an issue or pull request

By submitting content ideas and corrections you are agreeing they can be used in this workshop under the [Creative Commons Attribution ShareAlike 4.0 International license](https://creativecommons.org/licenses/by-sa/4.0/).  Attribution will be detailed via [GitHub contributors](https://github.com/practicalli/neovim/graphs/contributors).


## Sponsor my work

[![Sponsor practicalli-john](https://raw.githubusercontent.com/practicalli/graphic-design/live/buttons/practicalli-github-sponsors-button.png)](https://github.com/sponsors/practicalli-john/)

The majority of my work is focused on the [Practicalli series of books and videos](https://practical.li/) and an advisory role with several communities

Thank you to [Cognitect](https://www.cognitect.com/), [Nubank](https://nubank.com.br/) and a wide range of other [sponsors](https://github.com/sponsors/practicalli-john#sponsors) for your continued support


## GitHub Actions

The megalinter GitHub actions will run when a pull request is created,checking basic markdown syntax.

A review of the change will be carried out by the Practicalli team and the PR merged if the change is acceptable.

The Publish Book GitHub action will run when PR's are merged into main (or the Practicalli team pushes changes to the default branch).


## Local development

Install mkdocs using the Operating system package manager

```bash
sudo apt install mkdocs
```

Or via Python pip

```bash
pip install mkdocs
```

Install the plugins used by the Practicalli site using Pip (these are also installed in the GitHub Action workflow)

```bash
pip install mkdocs-material mkdocs-callouts mkdocs-glightbox mkdocs-git-revision-date-localized-plugin pillow cairosvg
```

> pillow and cairosvg python packages are required for [Social Cards](https://squidfunk.github.io/mkdocs-material/setup/setting-up-social-cards/)

Fork the practicalli/spacemacs GitHub repository and clone that fork to your computer,

```bash
git clone https://github.com/<your-github-account>/spacemacs.git

```

Run a local server from the root of the cloned project

```bash
mkdocs serve
```

The website will open at http://localhost:8000
