SPLATTR:=/data/ackley/PART4/code/D/SPLAT/blib/script/splattr
MFZRUN:=/data/ackley/PART4/code/D/MFM/bin/mfzrun
MFZGEOMETRY:={{2H2}}
MFZARGS:=$(MFZGEOMETRY) -cp 10.mfs
DIR:=$(shell pwd)
DEMO:=$(shell basename "$(DIR)")
SPLAT_FILES:=$(wildcard *.splat)
ULAM_FILES:=$(wildcard *.ulam)

MFZGEOMETRY:={{2H2}}
MFZARGS_TILES_MOVIE_ACC:=$(MFZGEOMETRY) -n -a 0 -p 30 -e 0 --accelerate 150 --warpfactor 1
MFZARGS_TILES_MOVIE_SURGE:=$(MFZGEOMETRY) -n -a 0 -p 30 -e 0 --accelerate 150 --surge 300 --warpfactor 1


run:	$(DEMO).mfz
	$(MFZRUN) $^ run $(MFZARGS)

$(DEMO).mfz:	$(SPLAT_FILES) $(ULAM_FILES) | Makefile* 
	$(SPLATTR) -g $^ $@

tilemovie:	$(DEMO).mfz
	$(MFZRUN) $^ run $(MFZARGS_TILES_MOVIE_ACC) -cp 10.mfs

clean:	FORCE
	rm -rf .gen .splatgen *~ ../*~

realclean:	clean
	rm -f *.mfz

.PHONY:	FORCE
