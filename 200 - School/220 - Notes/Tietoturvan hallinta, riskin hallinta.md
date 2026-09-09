Course: [[Tietoturvan perusteet]]
Date: **05-05-2026**

## Notes

### Mitä tietoturva tarkoittaa?

- Tietoturva tarkoittaa tietojen suojaamista **muutoksilta**, **tuhoutumiselta** ja **luvattomalta käytöltä**
- Tietoturvan käytännöt, teknologiat ja menettelyt eli **prosessit** auttavat organisaatioita varmistamaan, että:
	- Tietoja käytetään vain **oikeutetusti**
	- Tiedot ovat **saatavilla**, kun niitä tarvitaan
	- Tiedot ovat **oikeellisia** ja **muuttumattomia**
- Tietoturvan tavoite on suojata tärkeitä tietoja, kuten asiakirjoja, henkilötietoja ja liikesalaisuuksia
	- Tämä saavutetaan käyttämällä esimerkiksi **salausta**, **palomuureja**, **käyttöoikeuksien hallintaa** ja **turvallisuuskoulutusta**
- Tietoturva auttaa estämään tietojen väärinkäytön tai vuodon

### Mistä tietoturva rakentuu

- **Tietoturvapolitiikka** on organisaation virallinen julistus siitä, miten tietoturvaan liittyviä asioita käsitellään ja miten tietoturvaan liittyvät käytännöt ja menettelyt toteutetaan
- **Teknologiset ratkaisut** ovat erilaisia tietoturvamenetelmiä, kuten palomuureja, virustorjuntaohjelmia, salaustekniikoita ja käyttöoikeuksien hallintaa, joilla organisaatio voi suojata tietonsa
- Tietoturvaan liittyvät **käytännöt** ja **menettelyt** kattavat esimerkiksi tietojen käsittelyprosessit, käyttöoikeuksien hallinnan, salasanojen ja käyttäjätunnusten käytön, varmuuskopioiden säilyttämisen ja tuhoamisen
- **Tietoturvakoulutus** on tärkeä osa organisaation tietoturvaa. Henkilöstön tietoturvakoulutus auttaa henkilöstöä ymmärtämään tietoturvaan liittyvät riskit ja antaa heille tarvittavat tiedot ja taidot tietoturvan ylläpitämiseen.
- Tietoturva jakautuu kolmeen pääalueeseen:
	- **Luottamuksellisuus**
		- Luottamuksellisuudella tarkoitetaan tiedon suojaamista **luvattomalta pääsyltä**
		- Tiedot ja tietojärjestelmät ovat suojattuja ja niitä pääsee käyttämään vain **oikeutetut henkilöt tai järjestelmät**
		- Luottamuksellisuus saavutetaan erilaisten teknisten prosessien avulla kuten:
			- **Vahvat salaukset** tiedonsiirrossa ja tallennuksessa, **käyttöoikeuksien** hallinta, tietosuoja asetukset ja tietoturvakoulutus
	- **Eheys**
		- Eheys tarkittaa sitä, että tiedot säilyvät muuttumattomina, luotettavina ja virheettöminä
			- Muutokset vaativat valtuuden ja jokaisesta muutoksesta jää jälki
		- Tarkoitus estää tietojen tahaton tai tarkoituksellinen muuttuminen, väärentäminen tai vahingoittuminen
		- Toimia eheyden säilyttämiseksi:
			- Pääsyn hallinta
			- Todentamisprosessit
			- Tunkeutumisen havaitsemisjärjestelmät
			- Salaus
			- Tiivistetarkistukset
			- Rajapintojen rajoitukset, syötteiden ja funktioiden tarkistukset
			- Tietoturvakoulutus
	- **Saatavuus**
		- Saatavuus tarkoittaa, että tietojärjestelmät, palvelut ja resurssit ovat **käytettävissä aina tarvittaessa**
			- Saatavuuden varmistaminen tarkoittaa, että käyttäjät voivat käyttää tietojärjestelmiä ilman häiriöitä tai katkoksia
		- Tavoitteena on estää tai minimoida **palvelunestohyökkäykset**, **tekniset vianaiheet**, **luonnonkatastrofit**, inhimilliset virheet ja muut tekijä
			- Varmistamiseksi käytetään usein erilaisia toimenpiteitä, kuten **redundanssia**, **varmuuskopiointia**, **kuormanjakoa**, **häiriönsietokykyä** ja **vikasietoisuutta**

![[tietoturva_graph.png]]

- **AAA -prosessi**
	- **Identification** - tunnistaminen: Toimija ilmoittaa identiteettinsä järjestelmälle, jolloin AAA -prosessi käynnistyy
	- **Authentication** - todentaminen: Identiteetti varmennetaan sen perusteella mitä toimija tietää tai omistaa, tai mikä ominaisuus toimijalla on. Voidaan vaatia yksi tai useampi tekijä
	- **Authorization** - valtuutus. Järjestelmä myöntää toimijalle oikeuden päästä sisään järjestelmään, käyttää resursseja, päästä käsiksi tietoihin jne
	- **Auditting** – tarkastaminen. Käyttäjän pääsy ja tämän tekemät toimenpiteet kirjataan lokiin
	- **Accountability** – vastuullisuus. Kun AAA -prosessi on huolellisesti toteutettu, voidaan toimijaa pitää vastuullisena tekemisistään

### Tietosuoja

- Tietosuoja käsittelee vaik **yksilön yksityisyyden ja luottamuksen turvaamista**, sekä tämän tietojen suojaamista ja käsittelyä
- Tietosuoja on perustuslain turvaama oikeus, jokaiselle henkilölle

### Tieto-omaisuuden suojaaminen

- Tietoturva-standardit määrittelevät vaatimukset ja suositukset tietoturvan hallinnalle ja käytännöille organisaatiossa
- Tietoturvassa on paljon standardeja kuten esimerkiksi:
	- **ISO/IEC 27000 Standardiperhe** (ISO/IEC 27001 ja ISO/IEC 27002)
	- **NIST Cybersecurity Framework**: Yhdysvaltain National Institute of Standards and Technology (NIST)
	- PCI DSS: Payment Card Industry Data Security Standard (PCI DSS)
	- HIPAA: Health Insurance Portability and Accountability Act (HIPAA)
	- CIS Controls: Center for Internet Security (CIS)
	- ISO/IEC 15408: Common Criteria
	- IEC 62443: Industrial Automation and Control Systems (IACS)
	- FIPS: Federal Information Processing Standards
	- UL 2900
	- GDPR
	- eIDAs
	- FISMA

### Tietoturvan hallintakeinot

- **Estävät** (Preventive): pyrkii välttämään tapahtumaa
- **Havaitsevat** (Detective): tunnistaa tapahtumaan liittyvät tiedot
- **Korjaavat** (Corrective): Korjaa rikkinäisen osan järjestelmän kokonaan tapahtuman jälkeen
- **Varoittavat** (Deterrent): pyrkii estämään haitallisen toimijan tekemästä tapahtumaa
- **Palauttavat** (Recovery): pyrkii palauttamaan ympäristön nopeasti normaali tilaan tapahtuman jälkeen
- **Korvaavat** (Compensating): pyrkii tarjoamaan vaihtoehtoisen menetelmän

### Tiedon luokittelu

- Yksityisen sektorin tiedon luokittelu on aina organisaatiokohtaista:
	- **Julkinen** (Public)
		- Voidaan julkaista julkisissa medioissa
	- **Sisäinen** (Sensitive)
		- Ei haluta päästää organisaation ulkopuolelle
	- **Luottamuksellinen** (Private)
		- Ei saa päästää organisaation ulkopuolelle
		- Ei kuitenkaan täytä salaisen tiedon vaatimuksia
	- **Salainen** (Confidential, Proprietary)
		- Tiedon vuoto aiheuttaa erittäin vakavaa vahinkoa
		- Yleensä vain erityisesti nimettyjen henkilöiden saatavilla

### Riskienhallinta

- Riskienhallinta on järjestelmällistä toimintaa riskien rajoittamiseksi niin, että ne ovat optimisuhteessa riskien rajoittamisen kustannuksiin samalla kun organisaation toiminnalle asetetut tavoitteet voidaan saavuttaa
- Tietoturvariskeihin voi varautua:
	- Kartoittamalla riskit
	- Laatimalla tietoturvasuunnitelman
	- Sitoutumalla suunnitelman noudattamiseen
	- Pitämällä suunnitelman ja ohjeet ajantasaisena
	- Tietoturvakoulutuksella

![[riskienhallinta_graph.png]]

- Riskien suuruutta voi arvioida käyttämällä **Kvalitatiivista riskinanalyysiä**
	- Arvio ja tulokset ovat subjektiivisia ja perustuvat mielipiteisiin
	- Ei anna rahallista arvoa kustannus / hyöty-analyysiin
- Riskin suuruus = vakavuus * todennäköisyys

![[kvali_1.png]]
![[kvali_2.png]]
![[kvali_3.png]]

- Kvantitatiivinen riskianalyysi on menetelmä, jolla arvioidaan riskin toteutumisen aiheuttamat **kustannukset**
	- Laskelmat voivat olla monimutkaisia
	- Vaaditaan enemmän työtä yksityiskohtaisen tiedon saamiseksi

## References

- https://hhmoodle.haaga-helia.fi/pluginfile.php/4658103/mod_resource/content/10/Tietoturvan%20perusteet%20-%20ICI002AS2A%20-%20Moduli%201.pdf