all: syml
	pdflatex --output-directory=work -shell-escape test1.tex
	pdflatex --output-directory=work -shell-escape test2.tex

1: syml
	pdflatex --output-directory=work -shell-escape test1.tex

2: syml
	pdflatex --output-directory=work -shell-escape test2.tex

dir:
	@mkdir -p work

syml: dir
	@ln -sf ../figs work/figs

clean:
	@rm -rf ./work
	@rm -rf ./figs/*.dpth
	@rm -rf ./figs/*.log
	@rm -rf ./figs/*.dep
	@rm -rf ./figs/*.md5
	@rm -rf ./figs/*.pdf
