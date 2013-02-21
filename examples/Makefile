
# (1) You have to have ps2pdf (GhostScript) installed
# (2) You have to have muse2ps installed (http://muse2ps.ccarh.org)

BASE=beethoven-op018n1

all: from_msd from_pag

from_msd:
	@echo "Creating $(BASE)-01.pdf (automatic layout)"
	cat ../stage2/$(BASE)-01.msd | muse2ps =z16j \
		| ps2pdf -sPAPERSIZE=letter - - > $(BASE)-01.pdf

from_pag:
	@echo "Creating $(BASE)-01-pag.pdf (manual layout)"
	cat ../pages-score/$(BASE).pag | muse2ps =p \
		| ps2pdf -sPAPERSIZE=letter - - > $(BASE).pdf

clean:
	-rm $(BASE)-01.pdf
	-rm $(BASE).pdf

