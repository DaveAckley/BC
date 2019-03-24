SPLATTR:=/data/ackley/PART4/code/D/SPLAT/blib/script/splattr
MFZRUN:=/data/ackley/PART4/code/D/MFM/bin/mfzrun
MFZGEOMETRY:={{2H2}}
MFZARGS:=$(MFZGEOMETRY) -cp 10.mfs
DIR:=$(shell pwd)
DEMO:=$(shell basename "$(DIR)")
SPLAT_FILES:=$(wildcard *.splat)
ULAM_FILES:=$(wildcard *.ulam)

run:	$(DEMO).mfz
	$(MFZRUN) $^ run $(MFZARGS)

$(DEMO).mfz:	$(SPLAT_FILES) $(ULAM_FILES) | Makefile* 
	$(SPLATTR) -g $^ $@

clean:	FORCE
	rm -rf .gen .splatgen *~ ../*~

realclean:	clean
	rm -f *.mfz

.PHONY:	FORCE
