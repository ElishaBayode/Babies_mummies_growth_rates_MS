## This is the tsetse Growth MS folder

current: target
-include target.mk

# -include makestuff/perl.def

vim_session:
	bash -cl "vmt"

######################################################################

## commit.time: amsync

Sources += AveragingGrowthRate.tex

AveragingGrowthRate.pdf: AveragingGrowthRate.tex

Ignore += $(wildcard *.pdf)

######################################################################

### Makestuff

Sources += Makefile .gitignore

## Sources += content.mk
## include content.mk

Ignore += makestuff
msrepo = https://github.com/dushoff
Makefile: makestuff/Makefile
makestuff: makestuff/Makefile
makestuff/Makefile:
	ln -s ../makestuff .
	ls makestuff/Makefile

-include makestuff/os.mk

-include makestuff/texdeps.mk

-include makestuff/git.mk
-include makestuff/visual.mk
-include makestuff/projdir.mk
