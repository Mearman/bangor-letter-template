# Bangor University headed letter template

A LaTeX template for letters on Bangor University letterhead. It compiles on Overleaf with no install step: the package modules it needs sit in `vendor/`. This README uses controlled English. It is written in British English.

## Start on Overleaf

1. Press the green *Use this template* button on this repository. You get your own copy.
2. Open Overleaf and select *New Project*, then *Import from GitHub*.
3. Select your copy. Overleaf compiles it with pdfLaTeX at once.

If you use git on your own machine, clone your copy instead and run `latexmk -pdf main.tex`.

## Write your letter

Replace the sender details, the recipient block, and the body in `main.tex`. Set your school with the `\school` command and it appears under the wordmark. The `\bangorletterhead` command prints the crest, the wordmark, the school line, and a rule in the brand red. Put it at the top of each letter, before the `\opening` command.

## Keep the vendored modules current

The file `vendor/VERSION` shows which package release your copy carries. A scheduled workflow keeps it current: it pulls the latest package release into `vendor/`, compiles the letter against it, and lands the update directly when the result is green and the change stays inside `vendor/`. GitHub disables scheduled workflows after 60 days of repository inactivity. If you work only inside Overleaf, download the newest release of this template and copy the files in `vendor/` over your copies.

Never edit the files in `vendor/`. They are snapshots of the package repository, [Mearman/bangor](https://github.com/Mearman/bangor). A fix belongs there.

## Contribute

Make changes in the package repository, not in `vendor/` here. Commit messages follow the conventional commit format. Set up the hooks once per clone:

```sh
git config core.hooksPath .githooks
```

## Licence

The modules in `vendor/` are released under the LaTeX Project Public License, version 1.3c or later. See `vendor/LICENSE` in the package repository.

## Roadmap

Done:

- Worked example letter with the letterhead and the standard letter class.
- Vendored package modules with automatic vendor updates.
- CI that compiles the template.

Next:

- The horizontal crest variant as the letterhead asset, once the brand library provides the master.

At the CTAN switchover:

- This template stops vendoring and resolves against the installed package. The update workflow migrates your copy for you.
- A `-vendored` duplicate of this template keeps carrying the vendored copies, for people who want to tweak the module sources directly. Both variants stay available.
