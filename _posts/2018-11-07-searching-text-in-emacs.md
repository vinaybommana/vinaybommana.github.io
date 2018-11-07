---
layout: post
title:  "Searching Text in Emacs"
date:   2018-11-07
image: /assets/images/2018-11-07.jpg
---

## Using good old grep

press meta + x grep #Enter#

{% highlight bash%}
grep --color -nH --null -e "the Text you have to search for" *filetype
{% endhighlight %}

## Using rgrep

press meta + x rgrep #Enter#
{% highlight bash%}
search for: "Text"
{% endhighlight %}
the program is smart enough to ask for directory to search for

the following command is added automatically when we give the text to search for
and select all
{% highlight bash%}
find . -type d \( -path \*/SCCS -o -path \*/RCS -o -path \*/CVS -o -path \*/MCVS -o -path \*/.src -o -path \*/.svn -o -path \*/.git -o -path \*/.hg -o -path \*/.bzr -o -path \*/_MTN -o -path \*/_darcs -o -path \*/\{arch\} \) -prune -o \! -type d \( -name .\#\* -o -name \*.o -o -name \*\~ -o -name \*.bin -o -name \*.lbin -o -name \*.so -o -name \*.a -o -name \*.ln -o -name \*.blg -o -name \*.bbl -o -name \*.elc -o -name \*.lof -o -name \*.glo -o -name \*.idx -o -name \*.lot -o -name \*.fmt -o -name \*.tfm -o -name \*.class -o -name \*.fas -o -name \*.lib -o -name \*.mem -o -name \*.x86f -o -name \*.sparcf -o -name \*.dfsl -o -name \*.pfsl -o -name \*.d64fsl -o -name \*.p64fsl -o -name \*.lx64fsl -o -name \*.lx32fsl -o -name \*.dx64fsl -o -name \*.dx32fsl -o -name \*.fx64fsl -o -name \*.fx32fsl -o -name \*.sx64fsl -o -name \*.sx32fsl -o -name \*.wx64fsl -o -name \*.wx32fsl -o -name \*.fasl -o -name \*.ufsl -o -name \*.fsl -o -name \*.dxl -o -name \*.lo -o -name \*.la -o -name \*.gmo -o -name \*.mo -o -name \*.toc -o -name \*.aux -o -name \*.cp -o -name \*.fn -o -name \*.ky -o -name \*.pg -o -name \*.tp -o -name \*.vr -o -name \*.cps -o -name \*.fns -o -name \*.kys -o -name \*.pgs -o -name \*.tps -o -name \*.vrs -o -name \*.pyc -o -name \*.pyo \) -prune -o  -type f \( -name \* -o -name .\[\!.\]\* -o -name ..\?\* \) -exec grep --color -i -nH --null -e Text \{\} +
{% endhighlight %}


