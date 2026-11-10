# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.

# Minimal makefile for Sphinx documentation
#

JUPYTERBOOK   = jupyter book
SOURCEDIR     = source
SYNC_SHOTS    = python ../scripts/copy_doc_screenshots.py

# Put it first so that "make" without argument is like "make help".
help:
	@$(JUPYTERBOOK) --help

.PHONY: help Makefile serve sync-doc-screenshots

# Copy the galata documentation screenshots into the source tree before
# building, as the Jupyter Book build has no Sphinx setup() hook to do it.
sync-doc-screenshots:
	@$(SYNC_SHOTS)

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant to be a shortcut for $(SPHINXOPTS).
%: Makefile sync-doc-screenshots
	@$(JUPYTERBOOK) build --html

clean:
	# clean api build as well
	-rm -rf "$(SOURCEDIR)/api"
	@$(JUPYTERBOOK) clean

serve: sync-doc-screenshots
	@$(JUPYTERBOOK) start
