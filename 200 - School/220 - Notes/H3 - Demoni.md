---
class: "[[Palvelinten hallinta]]"
date: 14-04-2026
---

## Tiivistelmät

### Apache installed with Ansible

- Apache asennetaan ja konfiguroidaan Ansible-roolin avulla automaattisesti  
- Käytetään **package–file–service -mallia**:
  - paketti asennetaan (apache2)
  - konfiguraatiotiedostot kopioidaan
  - palvelu käynnistetään / restartataan  
- Muutokset config-tiedostoihin vaativat restartin `notify` kutsuu handleria  
- Roolin rakenne:
  - `tasks/` (asennus, kopiointi, linkitys)
  - `handlers/` (restart)
  - `files/` (konfiguraatiot)  
- Sivustoa voidaan palvella käyttäjän kotihakemistosta ilman sudoa  

### Ansible Documentation: Handlers
- Handlerit ovat tehtäviä, jotka suoritetaan vain jos muutos tapahtuu  
- Käytetään tyypillisesti palveluiden uudelleenkäynnistykseen  
- Eivät käynnisty automaattisesti ilman `notify`-kutsua  

### Notifying handlers
- Tehtävä ilmoittaa handlerille `notify`-avainsanalla  
- Handler suoritetaan vain, jos tehtävä tekee muutoksen (changed)  
- Sama handler suoritetaan korkeintaan kerran vaikka notify kutsutaan monta kertaa  
- Handlerin nimi yhdistää kutsun ja toiminnon  

### ansible-doc service

- Johdanto
  - `service`-moduulilla hallitaan palveluiden tilaa (start/stop/restart)  
  - Toimii eri init-järjestelmien kanssa (esim. systemd)

- enabled
  - Määrittää käynnistyykö palvelu automaattisesti bootissa  
  - Arvo: true / false  

- name
  - Palvelun nimi

- state
  - Palvelun tila:
    - started
    - stopped
    - restarted
    - reloaded  

- EXAMPLES
  - Esimerkeissä näytetään palvelun käynnistys, pysäytys ja automaattinen käynnistys  

## Tehtävä

### a)

- Ensin asennetaan `apache2`-paketti

```bash
$ sudo apt update
$ sudo apt install apache2
```

- Käynnistetään apache2 demoni

```bash
$ sudo systemctl start apache2
```

- Tarkistetaan, että apache2 toimii avaamalla selaimessa **http://localhost**. Näkyviin piätisi tulla apache2 oletussivu

![[H3 - Demoni_1.png]]

- Kun apache2 todetaan toimivaksi, niin poistetaan apache2:n konfiguraatiotiedostoista **/etc/apache2/sites-available/000-default.conf** ja lisätään tilalle oma **sivusto.com.conf** ja linkitetään se hakemistoon **/etc/apache2/sites-enabled/**

```bash
$ sudo rm /etc/apache2/sites-available/000-default.conf
$ sudo rm /etc/apache2/sites-enabled/000-default.conf

$ sudo touch /etc/apache2/sites-available/sivusto.com.conf
$ sudo ln -s /etc/apache2/sites-available/sivusto.com.conf /etc/apache2/sites-enabled/sivusto.com.conf
```

- Muokataan tiedostoa **sivusto.com.conf** siirtämään sivuston juuri kotihakemistoon

```bash
$ cat /etc/apache2/sites-available/sivusto.com.conf

<VirtualHost *:80>
        ServerName sivusto.com
        DocumentRoot /home/jerry/public_site/

        <Directory /home/jerry/public_site/>
                require all granted
        </Directory>
</VirtualHost>
```

- Käynnistetään apache2 uudelleen ja varmistetaan, että se tunnistaa uuden sivuston sijainnin avaamalla uudestaan selaimessa **http://localhost**

```bash
$ sudo systemctl restart apache2
```

![[H3 - Demoni_2.png]]

- Hakemistossa **/home/jerry/public_site** sijaitsee myös nettisivun index.html, jonka sisällä on sivun HTML-koodi
- Seuraavaksi muutetaan kotihakemiston, public_site-hakemiston sekä index.html:n oikeuksia, niin että muut käyttäjät voivat muokata niitä ilman sudo-oikeuksia

```bash
$ chmod ugo+x /home/jerry/
$ chmod ugo+x /home/jerry/public_site/
$ chmod ugo+r /home/jerry/public_site/index.html
```

- Kirjaudutaan toiselle käyttäjälle ja kokeillaan muokata sivua ilman sudo-oikeuksia

```console
$ ssh bob@localhost

$ nano /home/jerry/public_site/index.html
```

- Varmistetaan, että muutokset tulivat näkyviin **http://localhost**

![[H3 - Demoni_3.png]]

### b)

- Asennetaan `nginx`-paketti

```bash
$ sudo apt update
$ sudo apt install nginx
```

- Sammutetaan apache2-demoni ja käynnistetään nginx-demoni

```bash
$ sudo systemctl stop apache2
$ sudo systemctl start nginx
```

- Varmistetaan, että nginx toimii avaamalla selaimella **http://localhost**

![[h3_4.png]]

- Nginx konfiguraatio tiedostot ovat lähes identtiset apache2 tiedostoihin
- Muokataan tiedostoa **/etc/nginx/sites-available/default** siirtämään sivuston juuren kotihakemistoon
  - Sivuston luomisprosessi olisi identtinen edelliseen tehtävään, eli voimme käyttää vain samaa hakemistoa **/home/jerry/public_site**

```bash
$ sudo nano /etc/nginx/sites-available/default
```

- **default** tiedoston sisällä muokataan riviä **root /var/www/html;** ja muutetaan se **root /home/jerry/public_site;**
- Käynnistetään nginx-demoni uudelleen ja varmistetaan, että nginx tunnistaa uuden sivuston juuren tarkistamalla selaimessa **http://localhost**

![[h3_2.png]]

- Muokataan sivustoa toisella käyttäjällä ilman sudoa
  - Hakemistojen oikeudet on jo muokattu edellisessä tehtävässä, joten voimme heti kokeilla toisella käyttäjällä muokkaamista

```bash
$ ssh bob@localhost

$ nano /home/jerry/public_site/index.html
```

- Varmistetaan, että muutokset tulivat näkyviin **http://localhost**

![[h3_3.png]]

### c)

- Ensin luodaan ansible rooli nimeltä nginx ja luodaan sille oikea hakemistorakenne ja tiedostot

```bash
$ tree -F roles/nginx

roles/nginx/
└── tasks/
    └── main.yml
```

- Muokataan tiedostoa **main.yml** asentamaan nginx-paketti

```bash
$ cat /roles/nginx/main.yml

- apt:
    name: nginx
    state: present

- service:
    name: nginx
    state: started
    enabled: yes
```

- Lisätään rooli nginx tiedostoon **site.yml**, ajetaan ansible-playbook ja tarkistetaan, että nginx asentuu

```bash
$ ansible-playbook site.yml -K
```

![[h3_5.png]]

## Lähteet
- Tero Karvinen Apache installed with Ansible - quick notes. Luettavissa: https://terokarvinen.com/apache-ansible/ Luettu 14.4.2026
- Ansible Community Documentation. Luettavissa: https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_handlers.html Luettu: 14.4.2026