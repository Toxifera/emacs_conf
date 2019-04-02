This program will create a local package repository by from all
installed packages.

Please note compile Emacs lisp file (*.elc) from one version of Emacs
might not work with another version of Emacs. So you need this program
to compile package from local repository.

This is the ONLY way to 100% portable emacs setup.

Usage in Emacs,
`M-x elpamr-create-mirror-for-installed`
It should works out of box on latest Window 10, Linux, macOS.
If you use old Windows and native Windows Emacs, please install Cygwin
or MSYS2.

Usage in Shell,
  Emacs --batch -l ~/.emacs.d/init.el
        -l ~/any-directory-you-prefer/elpa-mirror.el \
        --eval='(setq elpamr-default-output-directory "~/myelpa")' \
        --eval='(elpamr-create-mirror-for-installed)

Use the repository created by elpa-mirror,
  - Insert `(setq package-archives '(("myelpa" . "~/myelpa/")))` into ~/.emacs
  - Restart Emacs

You can also setup repositories on Dropbox and Github.
See https://github.com/redguardtoo/elpa-mirror for HOW.
