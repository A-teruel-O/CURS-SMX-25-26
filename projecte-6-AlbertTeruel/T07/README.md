# T07: TransLògic — Administració Avançada i Seguretat Corporativa

## Breu descripció

### Introducció

Malgrat que l’encàrrec de **Projecte Nexus** consumeix bona part de la vostra energia i temps, no podeu deixar de banda els clients existents. **TransLògic S.A.** va confiar amb vosaltres per fer el salt a una infraestructura amb **Directori Actiu**, i ara cal rematar el projecte.

Cal realitzar una sèrie de millores crítiques en la seva infraestructura de xarxa. La direcció de l'empresa està preocupada per:

- La seguretat de les contrasenyes
- La mobilitat dels seus treballadors
- La gestió eficient del programari

A més, volen començar a **delegar certes tasques bàsiques** a un assistent tècnic sense donar-li privilegis totals d'administrador.

***

## Descripció de l'activitat

Heu de **documentar cada pas com si fos un informe tècnic d'implementació** per al client.
Abans de començar, **repenseu l’estructura d’unitats organitzatives (OU)** que vau presentar inicialment, ja que algun canvi podria simplificar les accions que caldrà realitzar.

***

### 1. Polítiques de seguretat i contrasenyes (Seguretat Corporativa)

El client exigeix **endurir la política de contrasenyes** per evitar accessos no autoritzats:

- **Política Global:**
Modifiqueu la *Default Domain Policy* perquè tots els membres del grup *personal* (és a dir, tot el domini) hagin de tenir una contrasenya de com a mínim **8 caràcters**.
- **Política per a Gerència:**
A la *Unitat Organitzativa (OU)* de la direcció (grup *gerencia*), creeu una **GPO específica** on:
    - La contrasenya sigui de **18 caràcters mínims**
    - Caduqui cada **28 dies**
    - **No** s'activi la complexitat
- **Millora Proactiva (Bonus):**
Proposeu i implementeu una **tercera GPO** útil per a una empresa logística (ex.: bloqueig automàtic de pantalla, fons d’escriptori corporatiu, etc.).
Justifiqueu la vostra decisió.

***

### 2. Desplegament automatitzat de programari

Per reduir els tiquets de suport tècnic, **automatitzeu la instal·lació d’eines segons el departament:**

- **Departament de Gestió:**
Els administratius (grup *gestio*) necessiten **7zip** per gestionar factures.
Creeu una GPO per **desplegar-la de forma assignada** (*s’instal·la automàticament*).
- **Departament de Gerència:**
Els directius (grup *gerencia*) necessiten un **navegador segur**.
Creeu una GPO per **desplegar Firefox de forma publicada** (*l’usuari pot instal·lar-lo des del Tauler de Control*).

**Nota tècnica:**
Els fitxers `.msi` es poden trobar a la carpeta de recursos compartits o descarregar-los manualment.

**Pregunta de consultoria:**
> El client pregunta: “Com podem crear els nostres propis fitxers `.msi` si una aplicació només ve amb un `.exe`?”
> Responeu aquesta qüestió dins l’informe.

***

### 3. Mobilitat d’usuaris (Perfils mòbils)

Els usuaris del departament de *gestio* canvien sovint entre portàtils i equips d’escriptori.

- Habiliteu una **carpeta compartida** al servidor anomenada `perfils`.
- Configureu la **plantilla d’usuari del grup gestio** perquè faci servir un **perfil mòbil** desat en aquesta carpeta.
- Creeu un **usuari nou de prova a gestio**, inicieu sessió i comproveu que s'ha creat la carpeta del seu perfil al servidor.

***

### 4. Seguretat de dades (Redirecció de carpetes)

Per evitar pèrdues de dades si un ordinador s'espatlla:

- Configureu una **directiva per a tot el domini** perquè la carpeta local **Documents** es redirigeixi a una ubicació de xarxa segura (*la carpeta home folder del servidor*).
- Verifiqueu que en desar un fitxer a *Documents* des del client, aquest **apareix al servidor**.

***

### 5. Delegació de funcions (Helpdesk)

**TransLògic S.A.** ha contractat un auxiliar de suport tècnic, però **no volen donar-li permisos complets**.

- Creeu un usuari **adminOU** dins la OU d'usuaris.
- Delegueu el control de la **OU principal (ex.: OU TransLogic)** a aquest usuari perquè només pugui:
    - Reiniciar contrasenyes dels treballadors.
    - Modificar pertinença als grups (*gestio*, *magatzem*, etc.*)

**Verificació:**
Demostreu amb captures que **adminOU** pot canviar contrasenyes però **no pot crear usuaris nous**.

***

## Què cal lliurar

### Informe tècnic

- Canvis en l’estructura de *Unitats Organitzatives* i justificació.
- Captures de pantalla comentades de cada pas (GPO creades, configuracions, logs d’auditoria, etc.).
- Justificació de la **3a GPO** triada i el benefici que aporta a *TransLògic*.
- Resposta sobre els **fitxers MSI** (com convertir o crear paquets MSI).
- **Proves de funcionament:**
    - `gpresult` mostrant les polítiques aplicades
    - Carpeta redirigida funcionant
    - Error en intentar crear usuari amb adminOU

***

## Material de suport

**0224 SOX.** Material UD7: AA1, AA2 i AA4 (*Moodle de l’assignatura*).

***

[Activitat](guia.md)
