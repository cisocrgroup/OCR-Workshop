# written 2015-04-14, US
# usage: make <target> FILE=<filename>

PDFS = $(patsubst %.md,%.pdf,$(wildcard *.md))

all: $(PDFS)

%.pdf: %.md
	pandoc $< \
	    --slide-level 2 \
	    --bibliography=include/ocropus.bib \
	    --latex-engine=xelatex \
	    -t beamer \
	    -H include/beamer-header.tex \
	    -o $@

.PHONY: clean
clean:
	rm *.pdf
