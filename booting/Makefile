CHAPTER  = booting
SRC      = $(CHAPTER).md
BIB      = chap0.bib
CSL      = ieee.csl
FILTER   = ../callout.lua

PANDOC   = pandoc
MMDC     = mmdc
PUPPETEER_CFG = /tmp/puppeteer-config.json

MMD_SRCS = $(wildcard images/*.mmd)
MMD_PNGS = $(MMD_SRCS:.mmd=.png)

PANDOC_FLAGS = --citeproc --bibliography=$(BIB) --csl=$(CSL)

# add callout filter if present
ifneq ($(wildcard $(FILTER)),)
PANDOC_FLAGS += --lua-filter=$(FILTER)
endif

.PHONY: all html pdf clean diagrams

all: diagrams pdf html

diagrams: $(MMD_PNGS)

images/%.png: images/%.mmd
	@if [ ! -f $(PUPPETEER_CFG) ]; then echo '{"args": ["--no-sandbox"]}' > $(PUPPETEER_CFG); fi
	$(MMDC) -i $< -o $@ -p $(PUPPETEER_CFG)

html: diagrams $(CHAPTER).html

$(CHAPTER).html: $(SRC) $(BIB) $(CSL) $(MMD_PNGS)
	$(PANDOC) $(PANDOC_FLAGS) --standalone -o $@ $<

pdf: diagrams $(CHAPTER).pdf

$(CHAPTER).pdf: $(SRC) $(BIB) $(CSL) $(MMD_PNGS)
	$(PANDOC) $(PANDOC_FLAGS) -o $@ $<

clean:
	rm -f $(CHAPTER).html $(CHAPTER).pdf
	rm -f $(MMD_PNGS)
