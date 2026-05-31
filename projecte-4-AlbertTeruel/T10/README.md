# T10: Servidor d’Impressió Linux — CUPS (Tasca individual)

## Introducció

Molt bé, equip. A la nostra consultora **EverPia**, busquem constantment optimitzar els recursos dels nostres clients per reduir costos i simplificar la gestió. Un dels punts més caòtics en qualsevol oficina és la gestió d’impressores: *drivers* incompatibles, costos de tòner descontrolats i equips que no saben a quina impressora estan enviant la feina.

La solució professional és implementar un **Servidor d’Impressió Centralitzat**.

**DevOptimize Solutions** ens ha demanat una proposta per centralitzar la impressió en tots els seus departaments, que utilitzen una barreja de clients **Linux (Zorin OS)** i **servidors (Ubuntu Server)**.

---

## La Vostra Missió: La Prova de Concepte (PoC)

Abans de comprar impressores de xarxa cares, el client vol veure una **Prova de Concepte (PoC)** que demostri que un servidor Linux pot gestionar una impressora i compartir-la de manera transparent amb els clients Zorin.

Per simular la impressora de xarxa sense gastar en maquinari, utilitzarem la **impressora virtual `cups-pdf`**.  
Aquesta eina actua com una impressora normal, però en lloc d’imprimir en paper, “imprimeix” el document en un fitxer PDF que es desa al servidor.

L’objectiu és configurar aquest escenari i demostrar que un client pot enviar una feina d’impressió al servidor.

---

## Escenari de Treball

El mateix escenari de la PoC de **NFS**. Podeu seguir usant les mateixes màquines.

- **Màquina 1 (Servidor):** Ubuntu Server configurat amb una interfície en NAT i una segona amb xarxa *Host-Only*.
- **Màquina 2 (Client):** Zorin OS (Desktop) amb la mateixa configuració de xarxa que el servidor.

---

## PoC (Prova de concepte)

1. Instal·lació de CUPS al servidor.  
2. Instal·lar impressora virtual.  
3. Configuració de l’administració de CUPS i permetre que CUPS escolti per totes les interfícies.  
4. Usant el navegador i el frontal web de CUPS, compartir la impressora.  
5. En el client Zorin, afegir la impressora.  
6. Fer una prova d’impressió de diversos documents.  
7. Comprovar al servidor com s’han generat els arxius PDF corresponents als treballs impresos.

---

## Documentació

Documenteu les comandes utilitzades, tal com s’ha explicat a la tasca en PDF, i incorporeu les **captures de pantalla** necessàries per demostrar el correcte funcionament de la prova.

[Guia](solucio.md)

[![Tornar al Projecte 4](https://img.shields.io/badge/Tornar_al_Projecte_4-0066cc.svg)](../README.md)

[![Tornar al README General](https://img.shields.io/badge/Tornar_al_README_General-4a5568.svg)](../../README.md)