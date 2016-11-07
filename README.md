# notes
notes on science

## How to use
To build an html view of the notes, one should install
* sphinx
* pandoc
* jupyter-notebook

> After installation, one can configure sphinx by following the instruction in [md/sphinx-config.md](md/2016-11-04-sphinx-config.md).

Without setting up sphinx, one can use the default sphinx setting in the repo (see conf.py, Makefile for details).

To build the html,
```
make html
```
And use web browser to view the htmls, e.g.
```
firefox _build/html/index.html
```
