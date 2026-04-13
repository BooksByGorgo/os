CHAPTER  = practical_locking
SRC      = $(CHAPTER).md
FILTER   = ../callout.lua

PANDOC   = pandoc

PANDOC_FLAGS =

# add callout filter if present
ifneq ($(wildcard $(FILTER)),)
PANDOC_FLAGS += --lua-filter=$(FILTER)
endif

.PHONY: all pdf clean

all: pdf

pdf: $(CHAPTER).pdf

$(CHAPTER).pdf: $(SRC) $(wildcard $(FILTER))
	$(PANDOC) $(SRC) -o $@ $(PANDOC_FLAGS) --pdf-engine=latexmk --pdf-engine-opt=-lualatex -V geometry:margin=1in

clean:
	rm -f $(CHAPTER).pdf
