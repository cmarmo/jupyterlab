# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.

# Minimal makefile for Sphinx documentation
#

JUPYTERBOOK   = jupyter book
SOURCEDIR     = source

# Put it first so that "make" without argument is like "make help".
help:
	@$(JUPYTERBOOK) --help

.PHONY: help Makefile serve

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
	@$(JUPYTERBOOK) build --html

clean:
	# clean api build as well
	-rm -rf "$(SOURCEDIR)/api"
	@$(JUPYTERBOOK) clean

start:
	@$(JUPYTERBOOK) start
