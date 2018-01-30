Papers and Notes
================
Bibliography and notes for attempting an Emacs-based paper reading process.  Based on the following:

- https://www.reddit.com/r/emacs/comments/4gudyw/help_me_with_my_orgmode_workflow_for_notetaking/
- https://codearsonist.com/reading-for-programmers

My initial `.emacs` additions for this are as follows:

```(setq org-ref-bibliography-notes "~/Documents/papers/notes/notes.org"
      org-ref-default-bibliography '("~/Documents/papers/references/references.bib")
      org-ref-pdf-directory "~/Documents/papers/pdfs/")

(setq bibtex-completion-bibliography
      '("~/Documents/papers/references/references.bib"))

(setq bibtex-completion-library-path '("~/Documents/papers/pdfs"))

(setq helm-bibtex-notes-path "~/Dropbox/papers/notes/notes.org")

(add-to-list 'auto-mode-alist '("\\.pdf\\'" . pdf-view-mode))

(add-hook 'bibtex-mode-hook (lambda () (local-set-key (kbd "C-c b") 'helm-bibtex)))
(add-hook 'bibtex-mode-hook (lambda () (local-set-key (kbd "C-c n") 'org-ref-open-bibtex-notes)))
(add-hook 'org-mode-hook (lambda () (local-set-key (kbd "C-c i") 'interleave-mode)))
(add-hook 'pdf-view-mode-hook (lambda () (linum-mode -1)))
```
