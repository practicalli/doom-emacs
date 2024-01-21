# Practicalli Doom Emacs

```none
██████╗ ██████╗  █████╗  ██████╗████████╗██╗ ██████╗ █████╗ ██╗     ██╗     ██╗
██╔══██╗██╔══██╗██╔══██╗██╔════╝╚══██╔══╝██║██╔════╝██╔══██╗██║     ██║     ██║
██████╔╝██████╔╝███████║██║        ██║   ██║██║     ███████║██║     ██║     ██║
██╔═══╝ ██╔══██╗██╔══██║██║        ██║   ██║██║     ██╔══██║██║     ██║     ██║
██║     ██║  ██║██║  ██║╚██████╗   ██║   ██║╚██████╗██║  ██║███████╗███████╗██║
╚═╝     ╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝   ╚═╝   ╚═╝ ╚═════╝╚═╝  ╚═╝╚══════╝╚══════╝╚═╝
```

## Project on hold

Practicalli is not actively developing this configuration, although it should be useable with current versions of Doom Emacs and Emacs 28 onward.


## Book status

[![MegaLinter](https://github.com/practicalli/doom-emacs/actions/workflows/megalinter.yml/badge.svg)](https://github.com/practicalli/doom-emacs/actions/workflows/megalinter.yml)
[![Publish Book](https://github.com/practicalli/doom-emacs/actions/workflows/publish-book.yaml/badge.svg)](https://github.com/practicalli/doom-emacs/actions/workflows/publish-book.yaml)
[![pages-build-deployment](https://github.com/practicalli/doom-emacs/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/practicalli/doom-emacs/actions/workflows/pages/pages-build-deployment)

![Ideas & issues](https://img.shields.io/github/issues/practicalli/doom-emacs?label=content%20ideas&logo=github)
![GitHub pull requests](https://img.shields.io/github/issues-pr-raw/practicalli/doom-emacs?label=pull%20requests&logo=github)

![GitHub commit activity](https://img.shields.io/github/commit-activity/y/practicalli/doom-emacs?label=commits&logo=github)


## Creative commons license

<div style="width:95%; margin:auto;">
  <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a>
  This work is licensed under a Creative Commons Attribution 4.0 ShareAlike License (including images & stylesheets).
</div>

## Overview

The Practicalli Doom Emacs provides practical guides to software development tasks, using predominantly the Clojure and ClojureScript languages.  Most of the editing techniques and tools are applicable to any editing tasks.

Doom Emacs is an open source project to provide configuration to add 150+ packages to Emacs, without having to writing a lot of common configuration code.

[![Discuss this guide on #practicalli channel of the Clojurians Slack community](images/practicalli-slack-channel.png)](https://clojurians.slack.com/messages/practicalli).

[Create a free Clojurians Slack community account](http://clojurians.net/).

This book will cover the following topics:
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

Issues and pull requests are most welcome.  Please detail issues as much as you can.  Pull requests are simpler to work with when they are specific to a page or at most a section.  The smaller the change the quicker it is to review and merge.

Please [see the detailed contributing section of the book](contributing.html) before raising an issue or pull request


* [Current Issues](https://github.com/practicalli/doom-emacs/issues)
* [Current pull requests](https://github.com/practicalli/doom-emacs/pulls)

[practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config/) GitHub repository contains the Practicalli Doom Emacs configuration used in this guide and issues and pull requests can also be made there.

## Contributing

Please [read the contributing section of the book](https://practical.li/doom-emacs/introduction/contributing/) page before raising an issue or pull request

By submitting content ideas and corrections you are agreeing they can be used in this workshop under the [Creative Commons Attribution ShareAlike 4.0 International license](https://creativecommons.org/licenses/by-sa/4.0/).  Attribution will be detailed via [GitHub contributors](https://github.com/practicalli/neovim/graphs/contributors).


## Sponsor Practicalli

[![Sponsor Practicalli via GitHub](https://raw.githubusercontent.com/practicalli/graphic-design/live/buttons/practicalli-github-sponsors-button.png)](https://github.com/sponsors/practicalli-johnny/)

All sponsorship funds are used to support the continued development of [Practicalli series of books and videos](https://practical.li/), although most work is done at personal cost and time.

Thanks to [Cognitect](https://www.cognitect.com/), [Nubank](https://nubank.com.br/) and a wide range of other [sponsors](https://github.com/sponsors/practicalli-johnny#sponsors) for your continued support


## GitHub Actions

The megalinter GitHub actions will run when a pull request is created,checking basic markdown syntax.

A review of the change will be carried out by the Practicalli team and the PR merged if the change is acceptable.

The Publish Book GitHub action will run when PR's are merged into main (or the Practicalli team pushes changes to the default branch).

Publish book workflow installs Material for MkDocs version 9


## Local development

Install mkdocs version 9 using the Python pip package manager

```bash
pip install mkdocs-material=="9.*"
```

Install the plugins used by the Practicalli site using Pip (these are also installed in the GitHub Action workflow)

```bash
pip3 install mkdocs-material mkdocs-callouts mkdocs-glightbox mkdocs-git-revision-date-localized-plugin mkdocs-redirects pillow cairosvg
```

> pillow and cairosvg python packages are required for [Social Cards](https://squidfunk.github.io/mkdocs-material/setup/setting-up-social-cards/)

Fork the GitHub repository and clone that fork to your computer,

```bash
git clone https://github.com/<your-github-account>/<repository>.git

```

Run a local server from the root of the cloned project

```bash
mkdocs serve
```

The website will open at <http://localhost:8000>
