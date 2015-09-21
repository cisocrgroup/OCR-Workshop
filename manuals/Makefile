# written 2015-09-08, US, FF
# usage: make <target>


PDFS = profiler-manual.pdf pocoto-manual.pdf

all: $(PDFS)
%.pdf: %.md
	pandoc -N --toc \
	--latex-engine=xelatex \
	-V papersize:a4paper \
	-V documentclass:scrartcl \
	-V classoption:DIV=12 \
    -V mainfont:"Linux Libertine O" \
    -V sansfont:"Linux Biolinum O" \
    --bibliography=../presentations/include/ocropus.bib \
    -t latex \
    -o $@ $<

.PHONY: clean
clean:
	$(RM) ../data/manuals/*.pdf
