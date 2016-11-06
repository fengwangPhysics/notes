source=$(wildcard *.md)
target=$(patsubst %.md,%.rst,$(source))

all: $(target)

%.rst: %.md
	pandoc $<  -S -s  -o $@
