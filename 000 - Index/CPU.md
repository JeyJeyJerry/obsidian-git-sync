**Class**: [[Johdanto ICT-infrastruktuuriin ja pilvipalveluihin]]
**Date**: 23.03.2025
**Topics**: #computer-architecture 

## Prosessorin toiminta
- Prosessori, eng. Central Processing Unit (CPU)
- CPU on tietokoneen tärkein osa. Se tekee suurimman osan työstä ja kontrolloi muita osia.
	- Alunperin CPU teki kaiken. Nykyisin monet osat sisältävät oman prosessorin, jotka huolehtivat erityisistä tehtävistä. Esim. näyttöadapteri ottaa osan CPU:n kuormituksesta.
- CPU ajaa ohjelmia. Ohjelman täytyy olla muistissa, kun CPU ajaa sitä. Ohjelman käynnistäminen tarkoittaa, että ohjelma ladataan keskusmuistiin levyltä. Sen jälkeen CPU alkaa ajaa ohjelmaa.
- Monet käyttöjärjestelmät ovat moniajojärjestelmiä. Se tarkoittaa, että useita ohjelmia ajetaan samanaikaisesti.
	- Itse asiassa CPU ajaa ainoastaan yhtä ohjelmaa kerrallaan. Järjestelmä vaihtaa ohjelmien välillä niin nopeasti, (n. 100 kertaa sekunnissa) että ohjelmat näyttävät olevan käynnissä yhtä aikaa.

## CPU:n historia
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
- Tärkein etu suuremmasta CPU:sta on parempi muistinhallinta