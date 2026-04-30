**Class**: [[Palvelinten hallinta]]
**Date**: 31.03.2026

## Tiivistelmät

### SSH public key

- Kirjautumisen automatisointi toimii niin, että ensin päivitetään järjestelmä ja sitten asennetaan open-ssh-server
- SSH-serveri laitetaan päälle komennolla "sudo systemctl enable --now ssh"
- Seuraavaksi testataan toimiiko serveri ottamalla yhteyttä localhostiin SSH:n avulla
- Lopuksi generoidaan avainpari ja kopioidaan se localhostiin, jotta kirjautuminen automatisoituu

### Hello Ansible

- Ansible on työkalu, jolla voi tehokkaasti konfiguroida suurta määrää tietokoneita samanaikaisesti
- Ansible toimii niin, että luodaan erilaisia ryhmiä, joihin lisätään tiettyjä tietokoneita
- Ryhmiin voi sitten ajaa erilaisia komentoja, jotka tekevät muokkauksia koneisiin SSH-yhteyden avulla

## Tehtävä

### a)

- Ensimmäisenä asennetaan **SSH-demoni**

![[h1_1.png]]

- Generoidaan SSH-avain komennolla `ssh-keygen`

![[h1_2.png]]

- Varmistetaan, että SSH-demoni toimii ottamalla SSH-yhteys localhostiin komennolla `ssh localhost`

### b)

![[h1_3.png]]

- Seuraavaksi automatisoidaan SSH-yhteys localhostiin kopioimalla julkinen SSH-avain
	- Localhostin, eli minun oman koneen SSH-avaimen kopioidaan komennolla `ssh-copy-id localhost`

![[h1_4.png]]

- Nyt SSH kirjautuminen pitäisi onnistua ilman salasanaa

![[h1_5.png]]

### c)

- Seuraavaksi valmistaudutaan tekemään Ansiblella "Hei Maailma"-testi asentamalla Ansible ja tarvittavat hyödylliset ohjelmat
	- `ansible`, `micro`, `bash-completion` ja `tree`

![[h1_6.png]]

- Luodaan Ansiblen tarvittava hakemistorakenne ja tiedosto `hosts.ini`
	- `hosts-ini`-tiedoston sisälle lisätään kaikki konfiguroitavat koneet
		- Tässä tapauksessa pelkästään **localhost**

![[h1_7.png]]

- Testataan, että Ansible toimii ajamalla jokaisella koneella (eli vain localhost) komento `uptime`
	- Tämä tehdään Ansiblella ajamalla komento `ansible all -a 'uptime' -i hosts.ini`, ansible-hakemiston sisällä

![[h1_8.png]]

- Luodaan ansible-kansion sisälle kansio **roles**, jossa sijaitsee kaikki roolit
- Luodaan roles-kansion sisälle rooli **hello**, jonka avulla teemme "Hei Maailma"- testin
- hello-roolin sisälle tulee kansio **tasks** ja sen sisälle tiedosto **main.yml**
	- Täällä sijaitsee kaikki roolikohtaiset konfiguraatiot
- main.yml-tiedoston sisälle kirjoitetaan koodia, joka käskee Ansiblea luomaan tiedoston **/tmp/hei_ansible** kaikille koneille ja kirjoittaa tiedoston sisälle "Hei Maailma!"

```bash
cat roles/hello/tasks/main.yml
```
```YAML
- copy:
    dest: /tmp/hei_ansible
    content: "Hei Maailma!"
```



## Lähteet
- Tero Karvinen SSH public key - Login without password. Luettavissa: https://terokarvinen.com/ssh-public-key-login-without-password/ Luettu 31.3.2026
- Tero Karvinen Hello Ansible. Luettavissa: https://terokarvinen.com/hello-ansible/ Luettu 31.3.2026