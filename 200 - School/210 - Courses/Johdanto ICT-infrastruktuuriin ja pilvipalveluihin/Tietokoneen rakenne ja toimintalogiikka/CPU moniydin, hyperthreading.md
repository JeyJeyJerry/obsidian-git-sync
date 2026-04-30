**Class**: [[Johdanto ICT-infrastruktuuriin ja pilvipalveluihin]]
**Date**: 23.03.2025

- Moniydin CPU tarkoittaa, että sama piiri sisältää useita prosessoreita. Esim. kaksiytiminen prosessori työskentelee kuten kaksi prosessoria.
- Moniydin CPU voi ajaa useaa ohjelmaa samanaikaisesti. Käyttöjärjestelmä hyödyntää SMP:tä (symmetric multiprocessing), joka pyrkii jakamaan kuorman tasaisesti useille ytimille tai prosessoreille.
- *Hyperthreading* on Intelin järjestelmä, joka ajaa useita operaatioita samanaikaisesti. Kaksiytiminen prosessori sisältää kaksi kokonaista CPU:ta, mutta hyperthreading:ssa vain osa CPU:sta on kahdennettu.
- Moniytimisyys ja hyperthreading voivat olla käytössä samalla piirillä. Intelin kaksiytiminen prosessori sisältää kaksi ydintä, jotka voivat käyttää Hyperthreading:a. Niinpä CPU toimii (lähes) kuin neljä erillistä prosessoria.