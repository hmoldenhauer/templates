all: thesis.pdf

thesis.pdf: thesis.tex content/*.tex tex/*
	mkdir -p build
	TEXINPUTS=build:.: lualatex --output-directory=build thesis.tex
	BIBINPUTS=build:.  biber build/thesis.bcf
	TEXINPUTS=build:.: lualatex --output-directory=build thesis.tex
	TEXINPUTS=build:.: lualatex --output-directory=build thesis.tex
	mv build/thesis.pdf thesis.pdf

clean:
	rm -rf build
