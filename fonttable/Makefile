
PKG = $(shell basename `pwd`)
FILES = README $(PKG).ins $(PKG).dtx
RESULTS = $(PKG).pdf $(PKG).sty

$(PKG).tar.gz: $(FILES) $(RESULTS)
	ctanify $(PKG).ins $(PKG).pdf README

$(PKG).pdf: $(PKG).dtx
	pdflatex -draftmode $<;
	makeindex -s gind.ist $(PKG);
	pdflatex -draftmode $<;
	pdflatex $<;

$(PKG).sty: $(FILES)
	tex $(PKG).ins

clean:
	git clean -dfx
