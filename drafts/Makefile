XML2RFC=xml2rfc
VERSION=03
DVERSION=10
TVERSION=00
VXLANVERSION=01
GENEVEVERSION=01
NSHVERSION=01
ETHVERSION=01
EXPORTVERSION=00
POTVERSION=02
IPV6VERSION=02
IPV4VERSION=00
DEPLOYVER=02
FLAGIETFVERSION=02
PROFILEVERSION=02
DEXVERSION=00
DEXIETFVERSION=00

all:	drafts

bootstrap: 
	sudo pip install xml2rfc
draft-ietf-ippm-ioam-data: draft-ietf-ippm-ioam-data.xml 
	$(XML2RFC) $< -o $@-$(DVERSION).txt
draft-ietf-sfc-proof-of-transit: draft-ietf-sfc-proof-of-transit.xml
	$(XML2RFC) $< -o $@-$(POTVERSION).txt
draft-ietf-sfc-ioam-nsh: draft-ietf-sfc-ioam-nsh.xml 
	$(XML2RFC) $< -o $@-$(NSHVERSION).txt
draft-brockners-ippm-ioam-vxlan-gpe: draft-brockners-ippm-ioam-vxlan-gpe.xml
	$(XML2RFC) $< -o $@-$(VXLANVERSION).txt
draft-brockners-ippm-ioam-geneve: draft-brockners-ippm-ioam-geneve.xml 
	$(XML2RFC) $< -o $@-$(GENEVEVERSION).txt
draft-weis-ippm-ioam-eth: draft-weis-ippm-ioam-eth.xml
	$(XML2RFC) $< -o $@-$(ETHVERSION).txt
draft-ietf-ippm-ioam-ipv6-options: draft-ietf-ippm-ioam-ipv6-options.xml
	$(XML2RFC) $< -o $@-$(IPV6VERSION).txt
draft-spiegel-ippm-ioam-rawexport: draft-spiegel-ippm-ioam-rawexport.xml 
	$(XML2RFC) $< -o $@-$(EXPORTVERSION).txt
draft-brockners-inband-oam-requirements: draft-brockners-inband-oam-requirements.xml 
	$(XML2RFC) $< -o $@-$(VERSION).txt
draft-gafni-ippm-ioam-ipv4-options: draft-gafni-ippm-ioam-ipv4-options.xml
	$(XML2RFC) $< -o $@-$(IPV4VERSION).txt
draft-mizrahi-ippm-ioam-flags: draft-mizrahi-ippm-ioam-flags.xml
	$(XML2RFC) $< -o $@-$(FLAGVERSION).txt
draft-ietf-ippm-ioam-flags: draft-ietf-ippm-ioam-flags.xml
	$(XML2RFC) $< -o $@-$(FLAGIETFVERSION).txt
draft-ioamteam-ippm-ioam-direct-export: draft-ioamteam-ippm-ioam-direct-export.xml
	$(XML2RFC) $< -o $@-$(DEXVERSION).txt
draft-ietf-ippm-ioam-direct-export: draft-ietf-ippm-ioam-direct-export.xml
	$(XML2RFC) $< -o $@-$(DEXIETFVERSION).txt
draft-mizrahi-ippm-ioam-profile: draft-mizrahi-ippm-ioam-profile.xml
	$(XML2RFC) $< -o $@-$(PROFILEVERSION).txt
draft-ioametal-ippm-6man-ioam-ipv6-deployment: draft-ioametal-ippm-6man-ioam-ipv6-deployment.xml
	$(XML2RFC) $< -o $@-$(DEPLOYVER).txt
data: draft-ietf-ippm-ioam-data.xml
	cp draft-ietf-ippm-ioam-data-$(DVERSION).txt versions/$(DVERSION)/
	ID-html-diffs draft-ietf-ippm-ioam-data-$(DVERSION).txt
	cp draft-ietf-ippm-ioam-data*html versions/$(DVERSION)/
encap: draft-brockners-ippm-ioam-vxlan-gpe draft-ietf-sfc-ioam-nsh draft-brockners-ippm-ioam-geneve draft-weis-ippm-ioam-eth draft-ietf-ippm-ioam-ipv6-options
	cp draft-weis-ippm-ioam-eth-$(ETHVERSION).txt versions/$(ETHVERSION)/
	cp draft-ietf-sfc-ioam-nsh-$(NSHVERSION).txt versions/$(NSHVERSION)/
	cp draft-brockners-ippm-ioam-vxlan-gpe-$(VXLANVERSION).txt versions/$(VXLANVERSION)/
	cp draft-brockners-ippm-ioam-geneve-$(GENEVEVERSION).txt versions/$(GENEVEVERSION)/
	cp draft-ietf-ippm-ioam-ipv6-options-$(IPV6VERSION).txt versions/$(IPV6VERSION)/

carlos: data encap

drafts: draft-ietf-ippm-ioam-data draft-brockners-inband-oam-requirements draft-ietf-sfc-proof-of-transit encap draft-spiegel-ippm-ioam-rawexport draft-ietf-ippm-ioam-flags draft-mizrahi-ippm-ioam-profile draft-ioamteam-ippm-ioam-direct-export draft-ioametal-ippm-6man-ioam-ipv6-deployment

.PHONY: clean draft commit
clean:
	/bin/rm -f *.txt

