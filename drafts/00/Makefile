XML2RFC=xml2rfc
VERSION=00

all:	drafts

bootstrap: 
	sudo pip install xml2rfc
draft-brockners-inband-oam-data: draft-brockners-inband-oam-data-$(VERSION).xml 
	$(XML2RFC) $< $@-$(VERSION).txt
draft-brockners-inband-oam-requirements: draft-brockners-inband-oam-requirements-$(VERSION).xml 
	$(XML2RFC) $< $@-$(VERSION).txt
draft-brockners-inband-oam-requirements: draft-brockners-inband-oam-requirements-$(VERSION).xml 
draft-brockners-inband-oam-transport: draft-brockners-inband-oam-transport-$(VERSION).xml 
	$(XML2RFC) $< $@-$(VERSION).txt
draft-brockners-proof-of-transit: draft-brockners-proof-of-transit-$(VERSION).xml
	$(XML2RFC) $< $@-$(VERSION).txt

drafts: draft-brockners-inband-oam-data draft-brockners-inband-oam-requirements draft-brockners-inband-oam-transport draft-brockners-proof-of-transit

.PHONY: clean draft commit
clean:
	/bin/rm -f *.txt

