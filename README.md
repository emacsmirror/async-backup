# async-backup
<a href="https://liberapay.com/contrapunctus/donate"><img alt="Donate using Liberapay" src="https://img.shields.io/liberapay/receives/contrapunctus.svg?logo=liberapay"></a>

[![MELPA](https://melpa.org/packages/async-backup-badge.svg)](https://melpa.org/#/async-backup)

Emacs has a built-in backup system, but it does not backup on each
save. It can be made to, but that makes saving really slow (and the
UI unresponsive), especially for large files.

Fortunately, Emacs has asynchronous processes.

To enable for all files -
  `(add-hook 'after-save-hook #'async-backup)`
  
To enable for a specific file -
  `M-x add-file-local-variable RET eval RET (add-hook 'after-save-hook #'async-backup nil t) RET`

# License
Chronometrist is released under your choice of [Unlicense](https://unlicense.org/) or the [WTFPL](http://www.wtfpl.net/).

(See files [UNLICENSE](UNLICENSE) and [WTFPL](WTFPL)).
