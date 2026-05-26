# T03: Servidor de fitxers

## Breu descripció

### Introducció

Quan el volum de negoci creix, també ho fa el volum de dades, i sovint aquí comencen els problemes. La informació es compartimenta, de manera que manca una visió global de la situació.
**FoodLogistic** no ha estat una excepció: cada departament guardava la documentació de forma local.
Per això, un dels requisits de l’encàrrec que heu rebut és solucionar aquest problema.

**Objectiu:** Implementar una infraestructura de fitxers segura, organitzada i amb control d'espai, utilitzant **permisos NTFS/SMB**, **quotes** i **filtratge de fitxers (FSRM)**.
Haureu de demostrar el domini de les tres vies d'administració: **Explorador de fitxers**, **Server Manager** i **PowerShell**.

***

## Descripció de l'activitat

L'activitat es divideix en fites que simulen el procés de consultoria i implementació real.

***

### 1. Preparació i Seguretat de Grups (AD)

Abans de crear el servidor de fitxers, cal preparar el terreny a l'**Active Directory**.
Treballareu sobre un domini `foodlogistic.test`, on es recomana crear una estructura de **OUs** coherent i justificada per les necessitats del projecte.

Creeu els següents grups de seguretat:

- **Administracio**: Gestió de factures i albarans
- **Transport**: Xofers i caps de flota
- **Direccio**: Gerència

***

### 2. Implementació de Recursos Compartits (Tres mètodes)

Heu de crear les següents estructures de carpetes al servidor, cadascuna amb un mètode diferent.

#### A. Carpeta **Public** (Mètode: Explorador d'arxius)

- Compartiu-la per a tothom.
- **Configuració:**
    - Permisos SMB: *Lectura*
    - Permisos NTFS: *Modificació*
    - Verifiqueu la combinació de permisos efectiva.


#### B. Carpeta **Operacions** (Mètode: Server Manager - FSSM)

- Instal·leu el rol **File and Storage Services** (si no hi és).
- Creeu el recurs compartit.
- Configureu perquè només es mostri als usuaris amb accés (**Access-Based Enumeration**).
- **Restricció:** Només el grup *Transport* hi pot accedir.


#### C. Carpeta **Confidencial** (Mètode: PowerShell bàsic)

- Creeu la carpeta `Direccio$` (recurs ocult).
- **Restricció:** Només hi pot accedir el grup *Direccio*.
- Utilitzeu el cmdlet `New-SmbShare` per compartir-la.
- Configureu una **GPO** perquè aquesta carpeta aparegui automàticament com a unitat **Z:**, només als usuaris de Direcció.


#### D. Carpeta **Confidencial** (Mètode: PowerShell avançat)

- Creeu la carpeta `Direccio`.
- **Restricció:** Només hi pot accedir el grup *Direccio*.
- Utilitzeu el cmdlet `New-SmbShare` per compartir-la i habiliteu **Access-Based Enumeration** amb PowerShell.
- Configureu una **GPO** perquè aparegui automàticament com a unitat **Z:** només als usuaris de *Direccio*.

> Heu de triar entre el mètode **C** o **D**. El mètode D té una valoració més alta.

***

### 3. Control d'Emmagatzematge (FSRM i Quotes NTFS)

El client es queixa que els usuaris guarden fotos personals i omplen el disc.
Heu d'actuar:

#### Quotes NTFS (Control per Volum)

- A la unitat de dades, activeu les **quotes NTFS** des de les propietats del volum.
- Establiu un límit de **500 MB** per defecte per a qualsevol usuari nou.


#### FSRM (Control per Carpeta)

- Instal·leu el rol **File Server Resource Manager**.
- **Quota de Carpeta:** A la carpeta **Public**, apliqueu una quota de **200 MB (Hard Quota)**.
- Configureu un avís al **90%** amb el missatge:

> "Compte! FoodLogístic t'informa que estàs a punt d'esgotar l'espai compartit."
- **Filtrat de Fitxers:** A la carpeta **Operacions**, creeu un filtre que impedeixi guardar fitxers:
    - Executables: `.exe`, `.msi`
    - Àudio o vídeo

***

### 4. Verificació i Auditoria

Connecteu-vos des d’un client **Windows 10/11** i comproveu:

- Verifiqueu l’accés i visibilitat dels recursos per un usuari de cada grup.
- Què passa si intenteu copiar un `.exe` a **Operacions**?
- Si canvieu l'extensió d'un executable a `.txt`, el servidor el deixa passar?
*(Proveu el filtratge actiu.)*

***

## Què cal lliurar

Es lliurarà un **informe tècnic detallat** en format **Markdown** que inclogui:

1. **Resum de Configuració**
Taula amb:
    - Nom de carpeta
    - Camí UNC
    - Grups amb accés
    - Mètode de creació utilitzat
2. **Evidències**
Captures i explicacions de les configuracions realitzades en els tres apartats.
3. **Proves de funcionament**
Comprovacions des dels clients on es verifiquin:
    - Controls d’accés
    - Quotes
    - Restriccions

***
