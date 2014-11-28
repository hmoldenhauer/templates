#ifdef $(build/thesis.bcf)
# need to define commands before processing
#endif

all: thesis.pdf

thesis.pdf: Makefile thesis.tex content/*.tex tex/* | build
	TEXINPUTS=build:.: lualatex --output-directory=build thesis.tex
	BIBINPUTS=build:.  biber build/thesis.bcf
	TEXINPUTS=build:.: lualatex --output-directory=build thesis.tex
	TEXINPUTS=build:.: lualatex --output-directory=build thesis.tex
	mv build/thesis.pdf thesis.pdf

build:
	mkdir -p build

clean:
	rm -rf build
