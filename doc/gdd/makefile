# David Saltares Márquez (C) 2011

# Project name
NOM=gdd

# Source
TEX=${NOM}.tex
TEXS=*.tex

# Temp TEX
TEXTTEMP=${TEX}.temp

# PDF Output filename
PDF=${NOM}.pdf

# Command
CTEX=pdflatex

# Options
TEXFLAGS=-file-line-error -halt-on-error

.PHONY: clean clear

# Build text to pdf Compilar el tex en pdf
#    Depends on .tex
#    Build twice to create index properly
$(PDF): $(TEX) $(TEXS)
	$(CTEX) $(TEXFLAGS) $(TEX) &&\
	$(CTEX) $(TEXFLAGS) $(TEX)

# First builds, then opens Evince to visualize PDF
view: $(PDF)
	evince $(PDF) &

# Cleans temp files
clear: 
	rm -rf *.aux *.dvi *.log *.idx *.toc *.out *.temp 

# Cleans all
clean: clear
	rm -rf *.pdf
