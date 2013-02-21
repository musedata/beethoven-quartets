# (1) You have to have muse2ps installed (http://muse2ps.ccarh.org)
#     To convert MuseData stage2 files or Music PaGe files into PostScript
#     files.
# (2) You have to have ps2pdf (GhostScript) installed to convert PostScript
#     files into PDF files.

BASE=beethoven-op018n1
BASE2=op018n1-01

all: from_msd from_pag parts

from_msd:
	@echo "Creating $(BASE)-01.pdf (automatic layout)"
	cat ../stage2/$(BASE)-01.msd | muse2ps =z16j \
		| ps2pdf -sPAPERSIZE=letter - - > $(BASE)-01.pdf

from_pag:
	@echo "Creating $(BASE)-01-pag.pdf (manual layout)"
	cat ../pages-score/$(BASE).pag | muse2ps =p \
		| ps2pdf -sPAPERSIZE=letter - - > $(BASE).pdf

parts: violin1 violin2 viola cello

violin1:
	@echo "Creating violin 1 part"
	cat $(BASE2)-p1-violin1.msd | muse2ps =z21j \
		| ps2pdf -sPAPERSIZE=letter - - > $(BASE2)-p1-violin1.pdf

violin2:
	@echo "Creating violin 2 part"
	cat $(BASE2)-p2-violin2.msd | muse2ps =z21j \
		| ps2pdf -sPAPERSIZE=letter - - > $(BASE2)-p2-violin2.pdf

viola:
	@echo "Creating viola part"
	cat $(BASE2)-p3-viola.msd | muse2ps =z21j \
		| ps2pdf -sPAPERSIZE=letter - - > $(BASE2)-p3-viola.pdf

cello:
	@echo "Creating cello part"
	cat $(BASE2)-p4-cello.msd | muse2ps =z21j \
		| ps2pdf -sPAPERSIZE=letter - - > $(BASE2)-p4-cello.pdf

clean:
	-rm $(BASE)-01.pdf
	-rm $(BASE).pdf
	-rm $(BASE2)-p1-violin1.pdf
	-rm $(BASE2)-p2-violin2.pdf
	-rm $(BASE2)-p3-viola.pdf
	-rm $(BASE2)-p4-cello.pdf

