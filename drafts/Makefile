XML2RFC=xml2rfc
VERSION=03
DVERSION=02
TVERSION=00
VXLANVERSION=00
GENEVEVERSION=00
NSHVERSION=01
GREVERSION=00

all:	drafts

bootstrap: 
	sudo pip install xml2rfc
draft-ietf-ippm-ioam-data: draft-ietf-ippm-ioam-data.xml 
	$(XML2RFC) $< -o $@-$(DVERSION).txt
draft-brockners-ippm-ioam-vxlan-gpe: draft-brockners-ippm-ioam-vxlan-gpe.xml
	$(XML2RFC) $< -o $@-$(VXLANVERSION).txt
draft-brockners-ippm-ioam-geneve: draft-brockners-ippm-ioam-geneve.xml 
	$(XML2RFC) $< -o $@-$(GENEVEVERSION).txt
draft-brockners-sfc-ioam-nsh: draft-brockners-sfc-ioam-nsh.xml 
	$(XML2RFC) $< -o $@-$(NSHVERSION).txt
draft-weis-ippm-ioam-gre: draft-weis-ippm-ioam-gre.xml
	$(XML2RFC) $< -o $@-$(GREVERSION).txt
draft-brockners-inband-oam-requirements: draft-brockners-inband-oam-requirements.xml 
	$(XML2RFC) $< -o $@-$(VERSION).txt
draft-brockners-proof-of-transit: draft-brockners-proof-of-transit.xml
	$(XML2RFC) $< -o $@-$(VERSION).txt
data: draft-ietf-ippm-ioam-data.xml
	cp draft-ietf-ippm-ioam-data-$(DVERSION).txt versions/$(DVERSION)/
	ID-html-diffs draft-ietf-ippm-ioam-data-$(DVERSION).txt
	cp draft-ietf-ippm-ioam-data*html versions/$(DVERSION)/
encap: draft-brockners-ippm-ioam-vxlan-gpe draft-brockners-sfc-ioam-nsh draft-brockners-ippm-ioam-geneve draft-weis-ippm-ioam-gre
	cp draft-weis-ippm-ioam-gre-$(GREVERSION).txt versions/$(GREVERSION)/
	cp draft-brockners-sfc-ioam-nsh-$(NSHVERSION).txt versions/$(NSHVERSION)/
	cp draft-brockners-ippm-ioam-vxlan-gpe-$(VXLANVERSION).txt versions/$(VXLANVERSION)/
	cp draft-brockners-ippm-ioam-geneve-$(GENEVEVERSION).txt versions/$(GENEVEVERSION)/

carlos: data encap

drafts: draft-ietf-ippm-ioam-data draft-brockners-inband-oam-requirements draft-brockners-proof-of-transit encap

.PHONY: clean draft commit
clean:
	/bin/rm -f *.txt

