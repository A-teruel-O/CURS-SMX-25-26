# Introducció al cas

A la tasca anterior heu dissenyat una política de còpies de seguretat pel nostre nou client **“Muntatges i Serveis Tècnics SL”**. Ara toca passar a l’acció i portar a la pràctica l’estudi anterior.

El client demana que s’elaborin unes **guies tècniques amb proves de concepte** per tal que el seu personal estigui qualificat per implantar el pla de còpies de seguretat.

***

## Part 1: Còpia de seguretat dels equips clients Windows

Encara que en principi el **DPR** no contemplaria fer còpia dels arxius locals dels equips clients, se’ns demana fer una excepció amb l’equip **Windows del director de l’empresa**.

En aquest equip es guarda informació important que no es vol tenir accessible al servidor de fitxers de l’empresa. Per aquest motiu és necessari definir una **política de còpies de seguretat seguint l’esquema 3-2-1**.

Es farà:

- Una còpia de seguretat a un **disc secundari** que té el propi equip.
- Una segona còpia al **cloud (Google Drive)** usant l’eina **Duplicati**.


### Prova de concepte

1. Creeu una màquina virtual **Windows 11** amb dos discos:
    - Un per instal·lar el sistema operatiu.
    - Un segon de **10 GB** per emmagatzemar les còpies de seguretat.
2. Per simular Google Drive, useu un compte que **no sigui el d’escola** (podeu crear un compte específic per a l’activitat).
3. Es desitja fer còpies de seguretat del **perfil de l’usuari**:
    - Cada **hora** al disc secundari.
    - A les **18:00** a Google Drive.
4. **Documenteu** el procediment:
    - Instal·lació de *Duplicati*.
    - Configuració dels plans de còpies.
    - Observació del funcionament.
5. Afegiu arxius a les carpetes de l’usuari, especialment a **Documents**.
6. Esborreu el contingut de *Documents* i procediu a fer una **restauració** des del disc secundari.
7. Comproveu com podeu fer una **restauració** des de la còpia emmagatzemada al *cloud*.

***

## Part 2: Còpia de seguretat al servidor Linux

Per fer les còpies del servidor Linux, la solució proposada pel vostre responsable és **Duplicity**, que permet fer còpies tant a un mitjà local com a un servidor remot.

Combinat amb el **planificador de tasques (cron)**, es poden implementar les polítiques de còpia que es desitgin.

### Prova de concepte

Per fer aquesta guia, usareu una **màquina virtual amb Ubuntu Server** i li afegireu un segon disc de **10 GB** que simularà una unitat auxiliar.

1. **Inicialitza i formata** el disc en format `xfs`.
Munteu-lo manualment a `/media/backup` (primer creeu la carpeta).
2. **Instal·la Duplicity.**
3. **Crea** un parell d’usuaris nous amb carpetes personals.
A la carpeta *home* del teu usuari, crea **4 arxius de 10 MB**.
4. Fes una **còpia de seguretat** de la carpeta `/home`.
5. Esborra els arxius i fes un **restore** per comprovar com es recuperen.
6. Afegeix un **nou arxiu de 4 MB** i fes una nova còpia.
Observa com ara ha fet una **còpia incremental**.
7. **Desmunta** la unitat de *backup*.

***

## Automatització del procés de còpies

Un aspecte molt important a nivell de seguretat és que la unitat de *backup* ha d’estar **per defecte desmuntada**.

El primer pas sempre serà **muntar la unitat**, i l’últim, **desmuntar-la** un cop s’ha fet la còpia.

### Scripts

1. **Crea un script `fullbackup.sh`** que faci:
    - Còpia completa de `/home`.
    - Emmagatzematge al volum muntat.
    - Ús de la variable d’entorn `PASSPHRASE`:

```bash
export PASSPHRASE=contrasenya
```

    - Dona **permisos d’execució** a l’script.
2. **Programa amb cron (com a root)** l’execució de l’script:
    - Els **diumenges a les 23:00**.
3. **Crea un script `incrementalbackup.sh`** que faci còpies incrementals de la mateixa carpeta.
    - Usa també la variable d’entorn `PASSPHRASE`.
    - Dona permisos d’execució.
4. **Programa amb cron (com a root)**:
    - L’execució de l’script de **dilluns a dissabte a les 23:00**.

- [Part 1 Windows](Part1.md)
- [Part 2 Ubuntu Server](Part2.md)

[![Tornar al Projecte 4](https://img.shields.io/badge/Tornar_al_Projecte_4-0066cc.svg)](../README.md)

[![Tornar al README General](https://img.shields.io/badge/Tornar_al_README_General-4a5568.svg)](../../README.md)