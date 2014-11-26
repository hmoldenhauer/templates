all: thesis.pdf

thesis.pdf: thesis.tex content/*.tex
	mkdir -p build
	TEXINPUTS=build:.: lualatex --output-directory=build thesis.tex
ifdef build/thesis.bcf
	BIBINPUTS=build:.  biber build/thesis.bcf
	TEXINPUTS=build:.: lualatex --output-directory=build thesis.tex
endif
	TEXINPUTS=build:.: lualatex --output-directory=build thesis.tex
	mv build/thesis.pdf thesis.pdf

clean:
	rm -rf build
