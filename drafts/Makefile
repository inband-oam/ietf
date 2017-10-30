XML2RFC=xml2rfc
VERSION=03
DVERSION=01
TVERSION=00

all:	drafts

bootstrap: 
	sudo pip install xml2rfc
draft-ietf-ippm-ioam-data: draft-ietf-ippm-ioam-data.xml 
	$(XML2RFC) $< -o $@-$(DVERSION).txt
draft-brockners-ioam-vxlan-gpe: draft-brockners-ioam-vxlan-gpe.xml 
	$(XML2RFC) $< -o $@-$(TVERSION).txt
draft-brockners-nvo3-ioam-geneve: draft-brockners-nvo3-ioam-geneve.xml 
	$(XML2RFC) $< -o $@-$(TVERSION).txt
draft-brockners-sfc-ioam-nsh: draft-brockners-sfc-ioam-nsh.xml 
	$(XML2RFC) $< -o $@-$(TVERSION).txt
draft-brockners-inband-oam-requirements: draft-brockners-inband-oam-requirements.xml 
	$(XML2RFC) $< -o $@-$(VERSION).txt
draft-brockners-inband-oam-requirements: draft-brockners-inband-oam-requirements.xml 
draft-brockners-proof-of-transit: draft-brockners-proof-of-transit.xml
	$(XML2RFC) $< -o $@-$(VERSION).txt
data: draft-ietf-ippm-ioam-data.xml
	cp draft-ietf-ippm-ioam-data-$(DVERSION).txt versions/$(DVERSION)/
	ID-html-diffs draft-ietf-ippm-ioam-data-$(DVERSION).txt
	cp draft-ietf-ippm-ioam-data*html versions/$(DVERSION)/
encap: draft-brockners-ioam-vxlan-gpe draft-brockners-sfc-ioam-nsh draft-brockners-nvo3-ioam-geneve
	cp draft-brockners-ioam-vxlan-gpe-$(TVERSION).txt versions/$(TVERSION)/
	cp draft-brockners-sfc-ioam-nsh-$(TVERSION).txt versions/$(TVERSION)/
	cp draft-brockners-nvo3-ioam-geneve-$(TVERSION).txt versions/$(TVERSION)/

carlos: data encap

drafts: draft-ietf-ippm-ioam-data draft-brockners-inband-oam-requirements draft-brockners-proof-of-transit draft-brockners-ioam-vxlan-gpe draft-brockners-sfc-ioam-nsh

.PHONY: clean draft commit
clean:
	/bin/rm -f *.txt

