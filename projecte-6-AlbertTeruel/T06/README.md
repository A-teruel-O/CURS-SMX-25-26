# T06: Projecte Nexus — Implantació de PKI i Signatura Digital Corporativa

## Breu descripció

### Introducció

Un cop heu resolt el problema de la **confidencialitat**, Projecte Nexus ha detectat una necessitat crítica: **garantir la integritat, autenticitat i el no repudi** dels seus documents interns i contractes amb proveïdors.

Fins ara signaven en paper, però volen **modernitzar-se**.
Us han demanat una **Prova de Concepte (PoC)** per demostrar que podeu muntar una infraestructura pròpia on els seus empleats puguin obtenir **certificats digitals corporatius** i signar documents PDF oficialment, **sense haver de comprar certificats a tercers** per a l'ús intern.

***

## Descripció de l'activitat

L'activitat es divideix en **tres fases principals**.
Treballareu en **parelles**: un de vosaltres gestionarà el **servidor (Administrador de Nexus)** i l'altre la **màquina client (Treballador de Nexus)**, col·laborant en tot el procés.

### Fases del projecte

1. **Fase 1:** Desplegament de la CA a Ubuntu Server
2. **Fase 2:** Sol·licitud i Emissió de Certificats pel client
3. **Fase 3:** Signatura Digital i Verificació (Acrobat Reader)

***

## Què cal lliurar

Al **repositori del projecte**, dins la carpeta corresponent a la tasca, heu de lliurar la següent feina:

### Memòria tècnica

- Format **Markdown** i nom: `memoria.md`
- Captures de pantalla comentades del procés d'instal·lació de l’**autoritat de certificació (CA)** a Ubuntu Server
- Documentació del procediment de **sol·licitud del certificat client**
- Procediment de **creació del certificat client**
- **Instal·lació de la clau CA** al client
- **Instal·lació del certificat client**
- Procediment de **signatura d’un document PDF** i **comprovació**
- Breu explicació de les diferències entre una **Clau Pública** i una **Clau Privada** en aquest procés


### Evidència de la signatura

- El **fitxer PDF de prova** de Nexus signat digitalment per un dels membres del grup
    - (S’haurà d’adjuntar al repositori)


### Certificat arrel

- El fitxer `.cer` de la vostra **Autoritat de Certificació (CA)**
    - (La clau pública de la CA, també s’haurà d'incloure al repositori per poder ser descarregat)

***

[Memoria](memoria.md)


