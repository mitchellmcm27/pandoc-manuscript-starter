[![Build Status](https://travis-ci.com/mitchellmcm27/pandoc-manuscript-starter.svg?branch=master)](https://travis-ci.com/mitchellmcm27/pandoc-manuscript-starter)

```sh
git clone --recurse-submodules https://github.com/mitchellmcm27/pandoc-manuscript-start your-paper-title
```

This is a starter kit for writing manuscripts in Markdown using Pandoc. Any text editor can be used to generate manuscripts, but a VS Code workspace is provided here.
This setup splits the process of creating a manuscript into two tasks:

For **writing**, we provide
* A bare-bones directory for organizing your manuscript files (see the `source` folder),
* The ability to write text fully in Markdown,
* Bibliography integration with BibTeX,
* Reference autocomplete (VS Code package `Pandoc Citer`),
* Thousands of pre-defined citation styles from CSL (`styles` submodule, see below)

For generating the final manuscript file (**building**)
* High quality output in pdf (or docx, or others) with Pandoc,
* Build locally with VS Code and the `vscode-pandoc` package,
* Automatically build pdfs, uploaded to GitHub Releases (see below), or
* Extend the project in any number of ways to integrate the build system of your choice.

Note that you can build pdfs from Markdown using LaTeX and pandoc on your computer, but this requires both to be installed and set up properly (along with any other packages or pandoc filters). Getting the right variables on your PATH can be a hassle, and a LaTeX distribution (with packages) can take up significant hard disk space. Additionally, it's nice to be able to write in Markdown anywhere, from any machine, even in the browser, with pdf and docx generated on commits. This is why the automatic builds with Travis are nice.

The included VS Code workspace settings assume you have LaTeX, pandoc, pandoc-citeproc, pandoc-fignos, and pandoc-eqnos installed and set up, but this can be modified (see `.vscode/settings.json`).

## Essential VS Code packages

* [vscode-pandoc](https://marketplace.visualstudio.com/items?itemName=DougFinke.vscode-pandoc) - run pandoc locally to build pdf, docx, etc.
* [Pandoc Citer](https://marketplace.visualstudio.com/items?itemName=notZaki.pandocciter) - autocomplete for Markdown references (eg @McMillan2017)
* [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) - kb shortcuts, autocomplete, clickable links, etc.

## Other VS Code packages

* [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) - in case you need to drop down into LaTeX syntax
* [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)

## Automatic citation styles and reference formatting

Thousands of bibliography and citation styles are provided in the `styles` folder (as .csl files). This folder is a clone of the [official Citation Style Language repository](https://github.com/citation-style-language/styles). To change the style, update the `csl` field in the YAML header of the manuscript. Note that many of the styles live in the `dependent` directory, for example, `"../styles/dependent/pnas.csl"`.

## Automatic builds with Travis

To trigger a build, setup a Travis account and link the forked repository to Travis. Builds will be triggered on new commits, according to the setup in `.travis.yml`. A default setup is provided that makes sure basic dependencies are available for generating pdfs. This step builds a pdf file, but you need to save it somehow. One option is to upload the pdf to Github Releases on a successful build. To do this, first run `travis setup releases` in the repository. Replace the provided encrypted API key in `.travis.yml` with the one generated. Push a new commit to trigger a release, and look for the pdf as a draft release in your repository. Another option is to upload the generated pdf to Dropbox [e.g. like this](https://labs.consol.de/travis/dropbox/2015/11/04/upload-travis-artifacts-to-dropbox.html).

## Step by step

1. Fork/clone this repository
2. Edit manuscript
3. Push your edits
4. Get pdf

Based on my [PhD thesis proposal](https://github.com/mitchellmcm27/phd-thesis-proposal)
