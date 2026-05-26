# 0226. RA3: Anàlisi vulnerabilitats

En aquesta activitat analitzarem les vulnerabilitats d'un sistema informàtic mitjançant una eina d'escaneig de vulnerabilitats. L'objectiu és identificar possibles punts febles en la seguretat del sistema i proposar mesures per a mitigar-los.[^1]

## Resultats d'aprenentatge i criteris d'avaluació

RA3. Aplica mecanismes de seguretat activa descrivint-ne les característiques i relacionant-les amb les necessitats d'ús del sistema informàtic.[^1]
CA3.3 Realitza actualitzacions periòdiques dels sistemes per a corregir possibles vulnerabilitats.[^1]

## Entorn de treball

Usarem una màquina virtual **OpenVAS** com eina d'anàlisi. Aquesta màquina la teniu disponible en forma `.ova` a la unitat de xarxa.[^1]
[OpenVAS](https://www.openvas.org/) és un producte de codi obert que permet realitzar escanejats de vulnerabilitats en sistemes informàtics; hi ha diversos nivells de llicència en funció de les funcionalitats que es vulguin utilitzar.[^1]

Com a màquina objectiu, usarem una màquina virtual Linux amb diverses vulnerabilitats conegudes.[^1]
Aquesta màquina també la teniu disponible en forma `.ova` a la unitat de xarxa; és la coneguda com a [metasploitable-2](https://sourceforge.net/projects/metasploitable/files/Metasploitable2/).[^1]

Si la baixeu d'Internet, descarregareu un `.zip` que conté únicament l'arxiu de disc, però no la màquina virtual completa.[^1]

## Preparació de l'entorn

### Equip a escannejar

1. Descarregueu la `.OVA` corresponent a `metasplotible-linux` al vostre equip.[^1]
2. Importeu la màquina virtual a **VirtualBox**, assegureu-vos que la ruta on importarà la màquina és la que voleu utilitzar.[^1]
3. Configureu la màquina per tal que utilitzi xarxa en mode "xarxa-NAT".[^1]
4. Inicieu la màquina, les credencials per defecte són:[^1]
    - Usuari: `msfadmin`
    - Contrasenya: `msfadmin`
5. Un cop iniciada la màquina, obriu una terminal i executeu la comanda:[^1]

```bash
ip a
```

per obtenir la IP assignada a la màquina.  Anoteu aquesta IP, ja que la necessitareu més endavant.[^1]

### Equip amb OpenVAS

1. Descarregueu la `.OVA` corresponent a OpenVAS al vostre equip.[^1]
2. Importeu la màquina virtual a **VirtualBox**, assegureu-vos de nou que la ruta on importarà la màquina és la que voleu utilitzar.[^1]
3. Configureu la màquina per tal que utilitzi dues interfícies de xarxa:[^1]
    - La primera en mode "xarxa-NAT" per tal de tenir connectivitat a Internet i amb la màquina objectiu.
    - La segona en mode "host-only" per tal de poder accedir a la interfície web des del vostre equip.
4. Inicieu la màquina, les credencials per defecte són:[^1]
    - Usuari: `admin`
    - Contrasenya: `admin`
5. Un cop iniciada la màquina, s'obrirà un menú d'inicialització.  En aquest menú, per exemple, us demanen la llicència, que podeu obviar amb l'opció `Skip`.  El que sí que caldrà fer són dues accions importants:[^1]
    - Definir l'usuari que usarem per entrar via web, per comoditat triarem un usuari `admin` amb contrasenya `admin`.[^1]
    - Configurar la xarxa de les dues interfícies, seleccionant en cadascuna d'elles l'opció `dhcp` de IPv4.  Finalment, anoteu les dues adreces.[^1]

En aquest vídeo teniu un exemple de com fer aquesta configuració inicial (està fet amb una versió anterior d'OpenVAS, però els passos són similars): **OpenVAS-configurar.mp4**.[^1]

## Procediment pràctic

### Anàlisi de vulnerabilitats

1. Mostra l’accés a OpenVAS via web amb les credencials creades anteriorment; veuràs que et surt un avís relatiu a la seguretat del certificat, ja que és un certificat autofirmat, que pots ignorar.[^1]
2. Afegeix la IP de la màquina vulnerable com a *Host*.[^1]
3. Configura un *Target* amb el *Host* del punt anterior, inclou les credencials de la màquina vulnerable per accedir via SSH i SMB.[^1]
4. Realitza una exploració de vulnerabilitats. Aquest procés pot ser lent; si veieu que us queda poc temps, cancel·leu l’anàlisi i treballeu amb els resultats obtinguts.[^1]

Al següent vídeo pots veure un exemple de tot el procés d'anàlisi de vulnerabilitats amb OpenVAS: **OpenVAS-scan.mp4**.[^1]

### Recollida de resultats

Un cop acabem l’exploració, OpenVAS ens mostra els resultats corresponents a la màquina; podem veure la descripció de la vulnerabilitat i altra informació significativa.  Al darrer vídeo pots veure com es mostren els resultats, tant de vulnerabilitats totals com per serveis.[^1]

Al vídeo pots veure un exemple de com visualitzar els resultats obtinguts: **OpenVAS-resultats.mp4**.[^1]

## Documentació de l'activitat

Documenta bé, en un arxiu de Google Docs (assegura't de compartir-lo amb el teu professor) o directament en format Markdown, a la carpeta corresponent del repositori GitHub del projecte, els punts següents:[^1]

- Documentació del procés d'anàlisi de vulnerabilitats seguit:[^1]
    - Configuració de la màquina vulnerable.
    - Configuració de la màquina OpenVAS.
    - Passos seguits per realitzar l'anàlisi.
- Analitza quatre vulnerabilitats trobades:[^1]
    - Descripció de la vulnerabilitat incloent el seu CVE.
    - Nivell de gravetat.
    - Possible explotació.
    - Mesures de mitigació proposades.

[Guia](guia.md)