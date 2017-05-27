PDFS = m00-introduction.pdf m01-pocoto.pdf m02-profiler.pdf

all: $(PDFS)

%.pdf: %.tex
	xelatex $<

.PHONY: clean
clean:
	$(RM) $(PDFS)
