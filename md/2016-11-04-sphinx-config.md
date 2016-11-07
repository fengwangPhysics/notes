## Sphinx configuration

__Feng Wang__

_Nov 04, 2016_

1. Install `sphinx` and related theme packages.
```
pip install sphinx --user
pip install sphinx_rtd_theme --user
```

__Note__: `sphinx_rtd_theme` provides a theme in readthedocs style. This is optional to install.

2. Run `sphinx-quickstart` in command line, and choose the default setting except __`mathjax`, which should be set to be yes to show math symbols__.
`Create Windows command file? (y/n)` may be turned off.

3. Open `conf.py` and at about line 124, disable the default theme and use the rtd theme.
```python
#html_theme = 'alabaster'
import sphinx_rtd_theme
html_theme = "sphinx_rtd_theme"
html_theme_path = [sphinx_rtd_theme.get_html_theme_path()]
```

__Note__: This step is optional.

4. Modify `index.rst` to add whatever you want to show. See http://www.sphinx-doc.org/en/1.4.8/tutorial.html#defining-document-structure

5. Change the `Makefile` to enable automatic building. Add following to `html` target
```
    cd md/ && make && cd ..
    cd jupyter/ && make && cd ..
```
so that the `Makefile`'s `html` look like this
```
.PHONY: html
html:
    cd md/ && make && cd ..
    cd jupyter/ && make && cd ..
    $(SPHINXBUILD) -b html $(ALLSPHINXOPTS) $(BUILDDIR)/html
    @echo
    @echo "Build finished. The HTML pages are in $(BUILDDIR)/html."
```


6. To update the contents
```
make html
```

7. To clean the contents (sometimes, rebuild is necessary to rebuild the links.
```
make clean
```
