## Mummies new ms subdirectory 2020 Jan 02 (Thu)

current: target
-include target.mk

# include makestuff/perl.def

######################################################################

# Content

vim_session:
	bash -cl "vmt"

Sources += $(wildcard *.tex)

Sources += svjour3.cls

$(Sources):
	$(CP) ../*/$@ .

## mummies.pdf: mummies.tex

Ignore += example.eps

######################################################################

### Makestuff

Sources += Makefile

## Sources += content.mk
## include content.mk

Ignore += makestuff
msrepo = https://github.com/dushoff
Makefile: makestuff/Makefile
makestuff/Makefile:
	cd .. && $(MAKE)
	ls ../makestuff/Makefile && /bin/ln -s ../makestuff 

-include makestuff/os.mk

## -include makestuff/wrapR.mk

-include makestuff/git.mk
-include makestuff/visual.mk
-include makestuff/projdir.mk

-include makestuff/texdeps.mk
