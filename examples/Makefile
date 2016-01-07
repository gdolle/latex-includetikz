all: 1 2

1: syml
	lualatex --output-directory=work -shell-escape test1.tex

2: syml
	pdflatex --output-directory=work -shell-escape test2.tex

dir:
	@mkdir -p work

syml: dir
	@cd work; \
	ln -sf ../figs .;\
	ln -sf ../autogen .;

clean:
	@rm -rf ./work
	@rm -rf ./figs/*.dpth
	@rm -rf ./figs/*.log
	@rm -rf ./figs/*.dep
	@rm -rf ./figs/*.md5
	@rm -rf ./figs/*.pdf
	@rm -rf ./autogen
	@rm -rf ./figs/autogen
