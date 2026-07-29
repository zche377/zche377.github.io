# Build the CV and install it where the site serves it from.
# `assets/cv/cv.tex` is the single source of truth; assets/pdf/cv_ziruichen.pdf
# is a build artifact that happens to be committed (GitHub Pages serves it).

TEX     := cv.tex
BUILD   := build
INSTALL := ../pdf/cv_ziruichen.pdf

.PHONY: all clean
all: $(INSTALL)

$(INSTALL): $(TEX)
	latexmk -pdf -interaction=nonstopmode -halt-on-error -output-directory=$(BUILD) $(TEX)
	cp $(BUILD)/cv.pdf $(INSTALL)

clean:
	latexmk -C -output-directory=$(BUILD) $(TEX)
	rm -rf $(BUILD)
