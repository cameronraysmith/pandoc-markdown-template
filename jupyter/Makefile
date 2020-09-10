.PHONY: typeset

typeset:
	pandoc                          \
	  --from         markdown       \
	  --to           latex          \
	  --template     template.tex   \
	  --out          jupyter.pdf \
	  --pdf-engine   xelatex        \
	  jupyter.md
