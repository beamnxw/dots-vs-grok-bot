TEX = dots_vs_grok_arxiv.tex
PDF = dots-vs-grok-bot.pdf

.PHONY: all clean

all: $(PDF)

$(PDF): $(TEX)
	pdflatex -interaction=nonstopmode $(TEX)
	pdflatex -interaction=nonstopmode $(TEX)
	cp dots_vs_grok_arxiv.pdf $(PDF)

clean:
	rm -f *.aux *.log *.out *.toc *.synctex.gz
