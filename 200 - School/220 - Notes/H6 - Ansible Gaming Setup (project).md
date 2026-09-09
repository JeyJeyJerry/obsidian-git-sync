Course: [[Palvelinten hallinta]]
Date: **05.05.2026**


## Mihin tarkoitukseen?

- Päivittää käyttöjärjestelmän
- Varmistaa, että uusimmat NVIDIA-ajurit ovat asennettu
- Aentaa `Discordin` ja `Steamin` 

## Käyttöohjeet

- **Playbookin** toimimista varten täytyy olla paketit `ansible`, `git` ja `openssh-server` asennettuna
- Paketit saa asennettua komenolla:

```bash
sudo apt install ansible git openssh-server
```

- Käynnistä **SSH-demoni** ja varmista, että se toimii komennoilla:

```bash
sudo systemctl enable --now ssh
sudo systemctl status ssh
```

- Kun demoni on päällä varmista vielä, että yhteys toimii komennolla:

```bash
ssh localhost
```

- Automatisoi SSH-kirjautuminen generoimalla SSH-avain:

```bash
ssh-keygen
ssh-copy-id localhost
```

- Tämän jälkeen kopioi varasto komennolla:

```bash
git clone https://github.com/JeyJeyJerry/ansible-gaming-setup.git
```

- Aja kopioidun kansion sisällä komento:

```bash
ansible-playbook site.yml -K
```

- Terminaalissa näkyy vaiheittain, mitä ohjelma tekee
- Latauksen päätyttyä koneellasi on asennettuna **Discord** ja **Steam** valmiina pelaamiseen

## Miten projekti toimii?

- Projektin hakemistorakenne on hyvin yksinkertainen

```bash
ansible-gaming-setup/
├── hosts.ini
├── ansible.cfg
├── site.yml
├── group_vars/
│   └── all.yml
└── roles/
    └── gaming/
        └── tasks/
            └── main.yml
```

- **hosts.ini**-tiedoston sisällä on kaikki koneet, joihin muutokset tehdään (tällä hetkellä vain localhost)
- **ansible.cfg**- tiedoston sisällä määritellään projektin **inventory**, joka tässä tapauksessa on **hosts.ini**
- **site.yml**-tiedoston sisällä määritellään mihin koneisiin mitkäkin roolit ajetaan
- **group_vars**-kansion sisällä tiedosto **all.yml**, sisältää linkit **Discordin** lataamista varten

### roles/gaming/tasks/main.yml

- Suurin osa konfiguraatiosta on tiedostossa **roles/gaming/tasks/main.yml**
- Kaikki vaiheet ovat myös varmistettu olevan **Idempotentteja**, eli ne tekevät muutokset vain tarvittaessa
- Ensimmäinen kohta korvaa koneella tiedoston **/etc/apt/sources.list**, joka määrittää mistä Debian hakee paketteja
  - **Steam** ja **Discord** tarvitsevat varastot `contrib`, `non-free` ja `non-free-firmware`, jotta ne voi asentaa oikein
 
```YAML
- name: check that contrib and non-free repos are enabled
  apt_repository:
    repo: "deb http://deb.debian.org/debian {{ ansible_distribution_release }} main contrib non-free non-free-firmware"
    state: present
```

- Seuraavat kaksi kohtaa päivittävät **pakettilistan** ja **järjestelmän**
  - Kohdat vastaavat komentoja `apt update` ja `apt full-upgrade`

```YAML
- name: update apt cache
  apt:
    update_cache: yes

- name: upgrade system
  apt:
    upgrade: dist
```

- Seuraavassa kolmessa vaiheessa tarkistetaan onko koneella **i386**-arkkitehtuuri, joka lisää 32-bit kirjastot, joita **Steam** tarvitsee
  - Jos arkkitehtuuria ei löydy, niin se lisätään ja pakettilista päivitetään uudestaan, jotta muutokset tulevat voimaan

```YAML
- name: check foreign architecture
  command: dpkg --print-foreign-architectures
  register: foreign_arch
  changed_when: false

- name: enable i386 architecture
  command: dpkg --add-architecture i386
  when: "'i386' not in foreign_arch.stdout"

- name: update apt cache after adding i386
  apt:
    update_cache: yes
```

- Loput vaiheet ovat yksinkertaisesti pakettien **Steam**, **Discord** ja **nvidia-driver** asennus
  - Ainoa poikkeava vaihe on **Discordin** asennus, jossa paketti haetaan Discordin omilta lataussivuilta linkkien avulla, jotka sijaitsevat tiedostossa **group_vars/all.yml**

```YAML
- name: install Steam
  apt:
    name: steam-installer
    state: present

- name: download Discord
  get_url:
    url: "{{ discord_url }}"
    dest: "{{ discord_deb_path }}"

- name: install Discord
  apt:
    deb: "{{ discord_deb_path }}"

- name: install NVIDIA drivers
  apt:
    name: nvidia-driver
    state: present
```

## Lähteet

- [terokarvinen.com](https://terokarvinen.com/)
- [Debian Wiki](https://wiki.debian.org/)
- [Debian Documentation](https://www.debian.org/doc/)
- [Ansible Documentation (apt, get_url, apt_repository, command, conditionals)](https://docs.ansible.com/)
- [How to install Steam on Debian](https://linuxcapable.com/how-to-install-steam-on-debian-linux/)
- [How to install Discord on Debian](https://linuxcapable.com/how-to-install-discord-on-debian-linux/)