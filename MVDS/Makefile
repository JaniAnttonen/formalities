WORKERS := 4

TLA := docker run --rm -it --workdir /mnt -v ${shell pwd}:/mnt talex5/tla

.PHONY: all check tlaps

all: check tlaps

# Run the TLC model checker
check:
	${TLA} tlc -workers ${WORKERS} MVDS.tla -config models/SpecOK.cfg

# Run the TLAPS proof checker
tlaps:
	${TLA} tlapm -I /usr/local/lib/tlaps MVDS.tla
