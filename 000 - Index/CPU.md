**Class**: [[Johdanto ICT-infrastruktuuriin ja pilvipalveluihin]]
**Date**: 23.03.2025
**Topics**: #computer-architecture 

- ## [[Prosessorin toiminta]]

## [[CPUn historia]]
- Ensimmäinen PC:n CPU oli Intel 8088. se oli yksinkertainen 16 bitin prosessori.
- Ensimmäinen 32 bitin prosessori oli Intel 80386 (or i386). Nykyiset prosessorit ovat tavallaan paranneltuja i386 prosessoreita. I386:n voi edelleen nähdä prosessoriperheen nimenä.
	- Intel Itanum on ensimmäinen 64 bittinen PC:n prosessori. Se ei ole yhteensopiva i368:n kanssa, eikä siitä syystä ole laajasti käytetty.
- AMD kehitti 64 bitin  laajennuksen  32 bitin prosessoriin. Useimmat prosessorit  (jopa Intel:n) käyttävät tätä laajennusta.
- Intel ja  AMD ovat pääasialliset PC prosessoreiden valmistajat
- ARM prosessori on Arm Ltd:n omistama teknologia, jota yritys lisenssoi muille  piirivalmistajille. ARM prosessoreita käytetään mm. mobiililaitteissa, sekä Applen tietokoneissa.

## CPU:n toiminta
- CPU voi olla 8, 16, 32 tai 64 bittinen.
	- Muut koot ovat harvinaisia. Ensimmäinen prosessori oli 4 bittinen.
- Bittien määrä (sananpituus) kertoo, kuinka suuren datamäärän CPU voi käsitellä kerrallaan.
	- Esim. 32 bittinen CPU voi käsitellä 64 bittiä tietoa, mutta se tehdään kahdessa osassa.
- 64 Bittinen CPU voi toimia kuten 32 tai 16 bittinen CPU.
- Tärkein etu suuremmasta CPU:sta on parempi muistinhallinta.
	- 8 bitin prosessori saattoi käyttää ainoastaan 64 kB (kilotavua) muistia.
	- 32 bittinen voi käyttää ainoastaan 4 GB (gigatavua)
	- 64 bittisissä CPU:ssa teoreettinen raja on hyvin suuri, mutta suurin osa prosessoreista rajoittaa muistin koon 256 GB:n tai pienemmäksi
	- (16 bitin prosessori saattoi hyödyntää 1 MB (megatavua) muistia, mutta ne käsittelivät muistin 64 kB paloissa tai segmenteissä)

## CPU:n kello
