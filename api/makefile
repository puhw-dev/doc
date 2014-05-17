OUTFILE=out/doc.pdf
OUTDIR=$(dir $(OUTFILE))

$(OUTFILE): doc.tex $(OUTDIR)
	pdflatex -output-directory $(OUTDIR) $<
	pdflatex -output-directory $(OUTDIR) $<

$(OUTDIR):
	mkdir -pv $(OUTDIR)

view: $(OUTFILE)
	chronic okular $^ &

spellcheck:
	aspell --mode=tex --lang=en --encoding=utf-8 check *.tex
	-egrep 'FIXME|TODO' *.tex *.m

clean:
	-rm -rv out

.PHONY: view spellcheck clean
