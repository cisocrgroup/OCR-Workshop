PDFS = m01-pocoto.pdf

all: $(PDFS)

%.pdf: %.tex
	xelatex $<

.PHONY: clean
clean:
	$(RM) $(PDFS)
