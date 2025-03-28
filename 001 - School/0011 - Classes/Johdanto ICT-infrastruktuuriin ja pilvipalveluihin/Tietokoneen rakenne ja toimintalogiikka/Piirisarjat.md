**Class**: [[Johdanto ICT-infrastruktuuriin ja pilvipalveluihin]]
**Date**: 29.03.2025
**Topics**: #computer-architecture 

- Piirisarja on "liima" emolevyn eri osien välillä.
	- Kontrolloi väyliä
	- Luo yhteyksiä
- Periteisesti piirisarja jaetaan kahteen osaan:
	- *North bridge*
	- Kontrolloi nopeita väyliä: CPU - RAM, PCIe, ...
	- Ennen piirisarja muodostui kahdestafyy sisestä piiristä, nykyisin vain yhdestä, silti puhutaan "sarjasta".
- *South bridge*
	- Kontrolloi hitaita väyliä
	- Sisältää useimmat oheislaitteiden liitynnät
- Nimitys "North" ja "South" tulevat siitä, että perinteisesti kaaviokuvassa prosessori on ylimmäisenä, sen alla north bridge ja alimmaisena south bridge.

![[piirisarja.png]]

- Piirisarja vaikuttaa tietokoneen nopeuteen.
- Piirisarja on prosessoririippuva.
	- Uudet prosessoriperheet tarvitsevat uudet piirisarjat
	- Piirisarja tukee vain rajoitettua määrää prosessorimalleja
	- AMD:n ja Intel:n prosessorit tarvitsevat omat piirisarjansa
- Emolevy rakentuu jonkin tietyn prosessoriperheen ja piirisarjan ympärille.