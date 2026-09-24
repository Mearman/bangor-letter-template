# Bangor University headed letter template
[![Open in Overleaf](https://img.shields.io/badge/Open_in_Overleaf-44A141?style=for-the-badge&logo=overleaf&logoColor=white)](https://www.overleaf.com/docs?snip_uri=https://github.com/Mearman/bangor-letter-template/archive/refs/heads/main.zip)
[![Use this template](https://img.shields.io/badge/Use_this_template-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Mearman/bangor-letter-template/generate)
[![Download ZIP](https://img.shields.io/badge/Download_ZIP-ED0000?style=for-the-badge&labelColor=231F20&logo=data:image/svg%2Bxml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxNiAxNiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ij48cmVjdCB4PSI3LjMiIHk9IjEiIHdpZHRoPSIxLjQiIGhlaWdodD0iNS41IiBmaWxsPSJ3aGl0ZSIvPjxwYXRoIGQ9Ik04IDEwLjUgNC43IDYuOGg2LjZaIiBmaWxsPSJ3aGl0ZSIvPjxwYXRoIGQ9Ik0yIDExLjV2MS44YTEuMiAxLjIgMCAwIDAgMS4yIDEuMmg5LjZhMS4yIDEuMiAwIDAgMCAxLjItMS4ydi0xLjhoLTEuNXYxLjVIMy41di0xLjVaIiBmaWxsPSJ3aGl0ZSIvPjwvc3ZnPg==)](https://github.com/Mearman/bangor-letter-template/archive/refs/heads/main.zip)

A LaTeX template for letters on Bangor University letterhead. It compiles on Overleaf with no install step: the class it needs sits in `vendor/`. This README uses controlled English. It is written in British English.

## Start on Overleaf

1. Press the *Open in Overleaf* badge above. Overleaf creates a project from this template and compiles it with pdfLaTeX at once. This path needs no GitHub account.
2. If you want your own git repository, press the *Use this template* badge or the green button instead, then import your copy into Overleaf from *New Project* and *Import from GitHub*.

If you use git on your own machine, clone your copy instead and run `latexmk -pdf main.tex`.

## Use it on your own TeX system

No git and no install step needed. Press the *Download ZIP* badge above, extract the archive, and run `latexmk -pdf main.tex` from the extracted folder. The `.latexmkrc` file beside `main.tex` points the compiler at `vendor/`, which is where the class and the crest live, so the project compiles as extracted.

The class is one file, `vendor/bangor.cls`, and it needs only the crest, `vendor/bangor-crest-colour.pdf`, beside it. The files that must stay together when you copy the project into your own setup are `main.tex`, `references.bib`, `continuation-markers.tex`, `.latexmkrc`, the whole `content/` folder, and the whole `vendor/` folder. If your editor runs `pdflatex` directly rather than through `latexmk`, set the `TEXINPUTS` environment variable to include `vendor//:` first, or point the editor at `latexmk`.


## Write your letter

Replace the sender details, the recipient block, and the body in `main.tex`. Set your school with the `\school` command and it appears under the wordmark. The `\bangorletterhead` command prints the crest, the wordmark, the school line, and a rule in the brand red. Put it at the top of each letter, before the `\opening` command.

## Keep the vendored class current

The file `vendor/VERSION` shows which package release your copy carries. A scheduled workflow keeps it current: it pulls the latest package release into `vendor/`, compiles the letter against it, and lands the update directly when the result is green and the change stays inside `vendor/`. GitHub disables scheduled workflows after 60 days of repository inactivity. If you work only inside Overleaf, download the newest release of this template and copy the files in `vendor/` over your copies.

Never edit the files in `vendor/`. They are snapshots of the package repository, [Mearman/bangor](https://github.com/Mearman/bangor). A fix belongs there.

## Contribute

Make changes in the package repository, not in `vendor/` here. Commit messages follow the conventional commit format. Set up the hooks once per clone:

```sh
git config core.hooksPath .githooks
```

## Licence

The class in `vendor/` is released under the LaTeX Project Public License, version 1.3c or later. See `vendor/LICENSE` in the package repository.

## Roadmap

Done:

- Worked example letter with the letterhead, using the letter option of the bangor class.
- A vendored copy of the class with automatic vendor updates.
- CI that compiles the template.

Next:

- The horizontal crest variant as the letterhead asset, once the brand library provides the master.

At the CTAN switchover:

- This template stops vendoring and resolves against the installed package. The update workflow migrates your copy for you.
- A `-vendored` duplicate of this template keeps carrying the vendored copies, for people who want to tweak the class source directly. Both variants stay available.
