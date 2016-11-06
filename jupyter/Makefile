source=$(wildcard *.ipynb)
target=$(patsubst %.ipynb,%.rst,$(source))

all: $(target)

%.rst: %.ipynb
	jupyter nbconvert $< --to rst
