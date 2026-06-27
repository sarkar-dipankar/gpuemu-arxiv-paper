PAPER := p1

# splncs04.bst forcibly initialises first names to "F.", which collapses
# distinct authors with the same surname (e.g. GEAK's two Liu authors:
# Ziqiong and Zicheng both render as "Liu, Z.") and drops the second
# component of hyphenated names (e.g. El-Mehdi -> E. instead of E.-M.).
# We post-process the bbl with sed to apply the canonical disambiguation
# the reviewer asked for, without overriding the LNCS bibliography style.

pdf:
	pdflatex -interaction=nonstopmode paper.tex
	bibtex paper
	sed -i \
	  -e 's/El~Arar, E\., Filip, S\.,/El~Arar, E.-M., Filip, S.-I.,/' \
	  -e 's/Ding, B\., Liu, Z\., Brahma/Ding, B., Liu, Ziqiong, Brahma/' \
	  -e 's/Li, D\., Liu, Z\., Barsoum/Li, D., Liu, Zicheng, Barsoum/' \
	  -e 's/Wang, H\., Zhang, J\., Jiang, K\., Wang, H\., Chen, J\., Zhu, J\.: {KernelBenchX}/Wang, Han, Zhang, J., Jiang, K., Wang, Haoxu, Chen, J., Zhu, J.: {KernelBenchX}/' \
	  paper.bbl
	pdflatex -interaction=nonstopmode paper.tex
	pdflatex -interaction=nonstopmode paper.tex

tarball: pdf
	tar czf arxiv-$(PAPER).tar.gz paper.tex refs.bib paper.bbl figures/

clean:
	rm -f paper.aux paper.log paper.out paper.toc paper.bbl paper.blg \
	      paper.pdf arxiv-$(PAPER).tar.gz

.PHONY: pdf tarball clean
