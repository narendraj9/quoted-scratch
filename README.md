# quoted-scratch


Beautiful quotes for your Emacs *scratch* buffer.

![Quotes](_assets/demo.gif?raw=true "Quotes")

## Installation

Clone this repository or download it as zip. Add it to your `load-path`:

      (add-to-list 'load-path "/path/to/quoted-scratch/dir/")


## Setup


```elisp
(require 'quoted-scratch)
(setq initial-scratch-message nil)

(add-hook 'emacs-startup-hook
            (lambda ()
              (run-with-timer 1 nil 'qs-refresh-scratch-buffer)
              (qs-refresh-quote-when-idle)))

;; You can add new quotes to the collection or have the Quote of the Day from
;; [http://quotes.rest/](http://quotes.rest).
;; For the latter:

(add-hook 'emacs-startup-hook
            (lambda ()
              (run-with-timer 1 nil 'qs-fetch-qod))

```

If you use `use-package`, add this to your init:

```
(use-package quoted-scratch
  :load-path "/path/to/quoted-scratch/dir/"
  :demand t
  :config
  (setq initial-scratch-message nil)
  (add-hook 'emacs-startup-hook
            (lambda ()
              (run-with-timer 1 nil 'qs-refresh-scratch-buffer)
              (qs-refresh-quote-when-idle))))

```

## Configuration

For configuring the look and feel of the displayed quotes, customize
the group `quoted-scratch` with `M-x customize-group`.
