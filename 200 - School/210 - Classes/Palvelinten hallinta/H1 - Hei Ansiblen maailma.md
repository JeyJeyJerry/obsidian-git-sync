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

- Ensimmäisenä asennetaan **SSH-demoni**

![[h1_1.png]]

- Generoidaan SSH-avain komennolla `ssh-keygen`

![[h1_2.png]]

- Varmistetaan, että SSH-demoni toimii ottamalla SSH-yhteys localhostiin komennolla `ssh localhost`

![[h1_3.png]]

- Seuraavaksi automatisoidaan SSH-yhte

## Lähteet
- Tero Karvinen SSH public key - Login without password. Luettavissa: https://terokarvinen.com/ssh-public-key-login-without-password/ Luettu 31.3.2026
- Tero Karvinen Hello Ansible. Luettavissa: https://terokarvinen.com/hello-ansible/ Luettu 31.3.2026