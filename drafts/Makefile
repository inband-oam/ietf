XML2RFC=xml2rfc
VERSION=03

all:	drafts

bootstrap: 
	sudo pip install xml2rfc
draft-brockners-inband-oam-data: draft-brockners-inband-oam-data.xml 
	$(XML2RFC) $< -o $@-$(VERSION).txt
draft-brockners-inband-oam-requirements: draft-brockners-inband-oam-requirements.xml 
	$(XML2RFC) $< -o $@-$(VERSION).txt
draft-brockners-inband-oam-requirements: draft-brockners-inband-oam-requirements.xml 
draft-brockners-inband-oam-transport: draft-brockners-inband-oam-transport.xml 
	$(XML2RFC) $< -o $@-$(VERSION).txt
draft-brockners-proof-of-transit: draft-brockners-proof-of-transit.xml
	$(XML2RFC) $< -o $@-$(VERSION).txt

drafts: draft-brockners-inband-oam-data draft-brockners-inband-oam-requirements draft-brockners-inband-oam-transport draft-brockners-proof-of-transit

.PHONY: clean draft commit
clean:
	/bin/rm -f *.txt

