.IGNORE:

TARGET = template

all: pdf

pdf: 
	pdflatex --synctex=1 -shell-escape 	$(TARGET)
	bibtex  				$(TARGET)
	pdflatex --synctex=1 -shell-escape 	$(TARGET)
	pdflatex --synctex=1 -shell-escape 	$(TARGET)
	pdflatex --synctex=1 -shell-escape 	$(TARGET)

authors.tex: authors.txt affils.txt
	python make-iop-author-list.py $^ > $@
	./arXiv-authors.sh

clean:
	/bin/rm -f *~ *.dvi *.log *.aux *.toc *.bbl *blg *.end *.out $(TARGET).synctex.gz $(TARGET)Notes.bib */*~ */*.dvi */*.log */*.aux */*.toc */*.bbl */*blg */*.end */*.out $(TARGET)Notes.bib
#	/bin/rm -f $(TARGET).ps $(TARGET).pdf 
