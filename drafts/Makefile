XML2RFC=xml2rfc
VERSION=03
DVERSION=08
TVERSION=06

all:	drafts

bootstrap: 
	sudo pip install xml2rfc
draft-brockners-inband-oam-data: draft-brockners-inband-oam-data.xml 
	$(XML2RFC) $< -o $@-$(DVERSION).txt
draft-brockners-inband-oam-transport: draft-brockners-inband-oam-transport.xml 
	$(XML2RFC) $< -o $@-$(TVERSION).txt
draft-brockners-inband-oam-requirements: draft-brockners-inband-oam-requirements.xml 
	$(XML2RFC) $< -o $@-$(VERSION).txt
draft-brockners-inband-oam-requirements: draft-brockners-inband-oam-requirements.xml 
draft-brockners-proof-of-transit: draft-brockners-proof-of-transit.xml
	$(XML2RFC) $< -o $@-$(VERSION).txt
data: draft-brockners-inband-oam-data
	cp draft-brockners-inband-oam-data-$(DVERSION).txt versions/$(DVERSION)/
	cp draft-brockners-inband-oam-data.xml versions/$(DVERSION)/draft-brockners-inband-oam-data-$(DVERSION).xml
	ID-html-diffs draft-brockners-inband-oam-data-$(DVERSION).txt
	cp draft-brockners-inband-oam-data*html versions/$(DVERSION)/
encap: draft-brockners-inband-oam-transport
	cp draft-brockners-inband-oam-transport-$(TVERSION).txt versions/$(TVERSION)/
	cp draft-brockners-inband-oam-transport.xml versions/$(TVERSION)/draft-brockners-inband-oam-transport-$(TVERSION).xml
	ID-html-diffs draft-brockners-inband-oam-transport-$(TVERSION).txt
	cp draft-brockners-inband-oam-transport*html versions/$(TVERSION)/

carlos: data encap

drafts: draft-brockners-inband-oam-data draft-brockners-inband-oam-requirements draft-brockners-inband-oam-transport draft-brockners-proof-of-transit

.PHONY: clean draft commit
clean:
	/bin/rm -f *.txt

