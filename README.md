# quoted-scratch


Beautiful quotes for your Emacs *scratch* buffer.

## Installation

Clone this repository or download it as zip. Add it to your `load-path`:

      (add-to-list 'load-path "/path/to/quoted-search/dir/")


## Setup


```elisp
(require 'quoted-search)

(add-hook 'emacs-startup-hook
            (lambda ()
              (run-with-timer 1 nil 'qs/refresh-scratch-buffer)
              (qs/refresh-quote-when-idle)))

```

If you use `use-package`, add this to your init:

```
(use-package quoted-scratch
  :load-path "/path/to/quoted-search/dir/"
  :bind ("C-. q" . qs/add-new-quote)
  :demand t
  :config
  (add-hook 'emacs-startup-hook
            (lambda ()
              (run-with-timer 1 nil 'qs/refresh-scratch-buffer)
              (qs/refresh-quote-when-idle))))

```

## Configuration

For configuring the look and feel of the displayed quotes, customize
the group `quoted-scratch` with `M-x customize-group`.
