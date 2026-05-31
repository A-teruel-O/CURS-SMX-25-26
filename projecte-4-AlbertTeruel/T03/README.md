# T03: Pla de recuperació davant desastres: imatges del sistema

## Descripció General
Arran de la necessitat de posar en marxa un Pla de Contingència i Continuïtat del Negoci per al client, es requereix el desplegament d'un Pla de Recuperació davant Desastres (DRP - *Disaster Recovery Plan*). Aquest pla té com a objectiu restaurar les dades, el maquinari i el programari crític de l'organització de la manera més ràpida possible davant d'un incident catastròfic per tal de repandre l'activitat normal.

Dins d'aquest escenari, s'ha d'assegurar que els treballadors disposin de forma immediata dels seus equips de treball en cas de robatori o avaria. Atès que els temps de posada en marxa són crítics per a l'àrea de negoci, la instal·lació manual del sistema operatiu i de les aplicacions no és una opció viable. Per aquest motiu, es treballarà en la creació i restauració d'imatges de sistema en un entorn corporatiu basat en GNU/Linux (Zorin OS 18).

---

## Estructura de la Tasca

### Fase 1: Anàlisi i Justificació de la Solució Tècnica
L'objectiu d'aquesta fase és investigar i comparar diferents eines del mercat que permetin crear imatges de disc completes per a la seva posterior restauració, mantenint les configuracions i aplicacions originals.

* **Desenvolupament:** Es realitzarà una comparativa detallada de 4 productes (2 de comercials i 2 de la comunitat o codi obert).
* **Criteris d'anàlisi:** S'han d'incloure de forma clara les característiques destacades i el preu de cada solució, evitant copiar textualment la informació de les pàgines web comercials.
* **Proposta tècnica:** El document ha de cloure amb una elecció raonada i justificada de la solució proposada per al client basant-se en les conclusions de la comparativa.

### Fase 2: Guia d'Ús Tècnica (Manual Operatiu)
Consisteix en l'execució d'una prova de concepte (PoC) individual utilitzant una màquina virtual (OVA) proveïda pel client que simula l'entorn de treball original.

* **Processos a realitzar i documentar:**
  * Creació d'una imatge completa del sistema original.
  * Restauració de la imatge en un sistema net (una màquina virtual idèntica en maquinari: RAM, processador, xarxa i mida de disc, però sense cap sistema operatiu instal·lat).
* **Eina obligatòria per a la PoC:** Es farà servir **Rescuezilla** per a la confecció d'aquest manual.
* **Format:** Cal redactar una guia tècnica detallada, acurada i correctament seqüenciada, incorporant captures de pantalla significatives per al personal de manteniment.

La tasca es realitza de forma estrictament individual.

---

## Materials i Links de Suport
* **INCIBE:** [¿Ya tienes tu Plan de Recuperación ante Desastres?](https://www.incibe.es/empresas/blog/tienes-tu-plan-recuperacion-desastres) (Article sobre plans de contingència, Agost 2019).
* **Eina de programari:** [Pàgina oficial de Rescuezilla](https://rescuezilla.com/).

[![Tornar al Projecte 4](https://img.shields.io/badge/Tornar_al_Projecte_4-0066cc.svg)](../README.md)

[![Tornar al README General](https://img.shields.io/badge/Tornar_al_README_General-4a5568.svg)](../../README.md)