# async-backup
<a href="https://liberapay.com/contrapunctus/donate"><img alt="Donate using Liberapay" src="https://img.shields.io/liberapay/receives/contrapunctus.svg?logo=liberapay"></a>

[![MELPA](https://melpa.org/packages/async-backup-badge.svg)](https://melpa.org/#/async-backup)

Emacs has a built-in backup system, but it does not backup on each
save. It can be made to, but that makes saving really slow (and the
UI unresponsive), especially for large files.

Fortunately, Emacs has asynchronous processes.

To enable for all files -
  `(add-hook 'after-save-hook #'async-backup)`

To enable for files in a specific directory -
  `M-x add-dir-local-variable RET <mode> RET eval RET (add-hook 'after-save-hook #'async-backup nil t) RET`

To enable for a specific file -
  `M-x add-file-local-variable RET eval RET (add-hook 'after-save-hook #'async-backup nil t) RET`

To backup your recentf file before each save -
```elisp
(advice-add 'recentf-save-list
            :before (lambda (&rest args) (async-backup recentf-save-file)))
```

# License
`async-backup` is released under your choice of [Unlicense](https://unlicense.org/) or the [WTFPL](http://www.wtfpl.net/).

(See files [UNLICENSE](UNLICENSE) and [WTFPL](WTFPL)).
