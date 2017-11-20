all: thesis.pdf

thesis.pdf: thesis.tex content/*.tex tex/* appendix/* #images/*
	mkdir -p build
	TEXINPUTS=build:.: lualatex --output-directory=build thesis.tex
	BIBINPUTS=build:.  biber build/thesis.bcf
	#makeglossaries -d build/ thesis
	TEXINPUTS=build:.: lualatex --output-directory=build thesis.tex
	TEXINPUTS=build:.: lualatex --output-directory=build thesis.tex
	mv build/thesis.pdf thesis.pdf

clean:
	rm -rf build
