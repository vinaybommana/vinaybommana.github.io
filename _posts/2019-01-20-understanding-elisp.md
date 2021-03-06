---
layout: post
title:  "Understanding Elisp"
date:   2019-01-20
excerpt: "Elisp conditionals and much more - Part 1"
tags: [Elisp, emacs]
comments: false
---

## making .emacs to read your own customizations

Add these following lines to your `.emacs` file this will load all the
`*.el` files in your `~/.emacs.d/lisp` directory.

	;; load custom files ;; from emacs stack exchange (defun load-directory
	(dir) (let ((load-it (lambda (f) (load-file (concat
	(file-name-as-directory dir) f))) )) (mapc load-it (directory-files dir
	nil "\\.el$")))) (load-directory "~/.emacs.d/lisp")

## conditionals

There are mainly four types of elisp conditionals.

-   if
-   which
-   unless
-   cond

### if (Special Form)

> `if` chooses between the then-form and the else-forms based on the
> value of condition. If the evaluated condition is non-nil, then-form
> is evaluated and the result returned. Otherwise, the else-forms are
> evaluated in textual order, and the value of the last one is returned.
> (The else part of if is an example of an implicit progn.)

> `if` condition has the value nil, and no else-forms are given, if
> returns nil.

	(if nil (print 'true) 'very-false)
> This returns `very-false`.

	(if evil-mode (powerline-raw (powerline-evil-tag) evil-face) )

### cond (Special Form)

    `cond` chooses among an arbitrary number of alternatives. Each *clause* in the `cond` must be a list.
The car of this list is the *condition*; the remaining elements, if any, the `body-forms`. Thus, a clause
looks like this:

    (condition body-forms...)

`cond` tries the clauses in textual order, by evaluating the *condition* of each clause.
If the *condition* is non-`nil`, the clause succeeds; then `cond` evaluates its *body-forms*,
and returns the value of the last of *body-forms*. Any remaining clauses are ignored.

    (condition)

Then, if *condition* is non-`nil` when tested, the `cond` form returns the value of *condition*.

If every *condition* evaluates to `nil`, so that every clause fails,
`cond` returns `nil`.

The following example has four clauses, which test for the cases where the value of `x` is a number,
string, buffer and symbol, respectively:

    (cond ((numberp x) x)
          ((stringp x) x)
          ((bufferp x)
           (setq temporary-hack x); multiple body-forms
           (buffer-name x))       ; in one clause
           ((symbolp x) (symbol-value x)))

Often we want to execute the last clause whenever none of the previous clauses was successful.
To do this, we use `t` as the condition of the last clause, like this: `(t body-forms)`.
The form `t` evaluates to `t`, which is never `nil`, so this clause never fails, provided the `cond` gets to it at all.
For example:

    (setq a 5)
    (cond ((eq a 'hack) 'foo)
          (t "default"))

output is `"default"`
This cond expression returns `foo` if the value of `a` is hack, and returns the string `"default"` otherwise.

Any conditional construct can be expressed with `cond` or with `if`.
Therefore, the choice between them is a matter of style. 
For example:

    (if a b c)
    ==
    (cond (a b) (t c))
