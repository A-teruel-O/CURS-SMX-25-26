# T07: Instal·lant un servidor de noms 

Després de l’exitosa experiència a nivell de formació, el nostres clients de **Digicore** estan tan satisfets amb la nostra feina que ens encarreguen la implantació des de zero dels seus serveis de **DNS** interns.

Actualment, l'agència fa servir adreces IP per accedir als seus servidors de desenvolupament, bases de dades i eines de gestió interna. Aquest mètode és ineficient i propens a errors:

* **Usabilitat deficient:** Els empleats han de memoritzar o buscar constantment adreces IP complexes (p. ex., 192.168.10.25).
* **Manteniment feixuc:** Si un servidor canvia la seva IP, cal notificar i actualitzar manualment la configuració a tots els equips i aplicacions que s'hi connecten.
* **Manca de professionalitat:** En un entorn professional, tots els serveis haurien de ser accessibles mitjançant noms fàcils de recordar.

---

Per tant, la nostra missió és implementar un Sistema de Noms de Domini (**DNS**) intern robust. L'objectiu és que els servidors i aplicacions de l'agència es puguin accedir utilitzant noms de domini amigables (p. ex., `bbdd.digicore.lan` o `wiki.digicore.lan`).

[![Tornar al Projecte 3](https://img.shields.io/badge/Tornar_al_Projecte_3-0066cc.svg)](../README.md)

[![Tornar al README General](https://img.shields.io/badge/Tornar_al_README_General-4a5568.svg)](../../README.md)