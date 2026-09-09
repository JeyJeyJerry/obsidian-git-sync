class: "[[Johdanto ICT-infrastruktuuriin ja pilvipalveluihin]]"
Date: 29-03-2025

- RAM-muisti on muistimoduuleilla. Muistimoduulit asennetaan emolevyn kantoihin.
- Pöytäkoneet käyttävät DIMM - ja kannettavat koneet SO-DIMM moduuleja.
- Moduulien valinta voi olla hankalaa. On monia parametreja, joita täytyy tarkastella.
	- Fyysinen koko: SO-DIMM, DIMM (huom! on useita DIMM - versioita)
	- Teknologia: DDR, DDR2, DDR3, ...
	- Nopeus: joko MHz tai tavua sekunnissa
		- 800 MHz tarkoittaa, että CPU voi lukea muistista tai kirjoittaa muistiin 800 000 000 kertaa sekunnissa. Prosessori siirtää 8 tavua yhtä aikaa. Niinpä siis CPU siirtää 6400 MB/s.
	- Koko: gigatavuja (2, 4, 8, 16, ...)
	- Virheenkorjaus: palvelimet käyttävät moduuleja joissa on ECC (Error Correction Code). Työasemat eivät voi niitä käyttää.
	- Paras tapa valita moduuli on katsoa emolevyn valmistajan tai muistin valmistajan suosituksia.