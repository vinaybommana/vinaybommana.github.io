---
layout: post
title:  "Understanding ELisp"
date:   2019-01-20
excerpt: "ELisp for Emacs customizations"
tags: [Emacs, ELisp]
comments: false
---

## making .emacs to read your own customizations

Add these following lines to your `.emacs` file
this will load all the `*.el` files in your `~/.emacs.d/lisp` directory.

{% highlight elisp %}

;; load custom files
;; from emacs stack exchange
(defun load-directory (dir)
	(let ((load-it (lambda (f)
			(load-file (concat (file-name-as-directory dir) f)))
			))
(mapc load-it (directory-files dir nil "\\.el$"))))
(load-directory "~/.emacs.d/lisp")

{% endhighlight %}

## Conditionals
There are mainly four types of elisp conditionals.
* if
* which
* unless
* cond


1. if (Special Form)

> `if` chooses between the then-form and the else-forms based on the value of condition. If the evaluated condition is non-nil, then-form is evaluated and the result returned. Otherwise, the else-forms are evaluated in textual order, and the value of the last one is returned. (The else part of if is an example of an implicit progn.

> `if` condition has the value nil, and no else-forms are given, if returns nil. 

{% highlight elisp %}
(if nil
	(print 'true)
'very-false)

{% endhighlight %}
> This returns `very-false`.

{% highlight elisp %}

(if evil-mode
  (powerline-raw (powerline-evil-tag) evil-face)
)
{% endhighlight %}

## lists


## functions
