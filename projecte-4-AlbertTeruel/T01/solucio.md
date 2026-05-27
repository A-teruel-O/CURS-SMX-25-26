***

### Fase 1: Treball individual

1. Què copiar i priorització
Les dades més crítiques són les bases de dades de Comptabilitat i Clients perquè s’utilitzen cada dia i canvien constantment. Després, també són importants els documents dels projectes i els plànols. Les carpetes personals dels usuaris són útils, però si algun dia se’n perd alguna, no és tan greu.
No caldria fer còpia de seguretat dels 10 equips clients senceres, només dels documents rellevants que alguns tècnics guarden temporalment. La major part ja s’emmagatzema al servidor.
2. Periodicitat i tipus de còpia

- Bases de Dades (crítiques): còpia incremental cada 4 hores i una còpia completa cada dia a la nit.
- Documents de projectes i carpetes personals: còpia diferencial diària i completa setmanal (diumenge).

Això permet tenir les dades més importants sempre actualitzades i evitar un excés d’espai ocupat.

3. Mitjans i ubicació
S’utilitzaran discs durs externs (NAS) per a la còpia local i Cloud (Google Drive o Azure) com a còpia externa.
Seguint la regla 3-2-1:

- 3 còpies totals: dades originals + còpia local + còpia al núvol.
- 2 tipus de mitjans: NAS i Cloud.
- 1 còpia fora de lloc: al núvol (fora de l’oficina).

***

### Fase 2: Treball per trio

| Element | Proposta del trio | Justificació |
| :-- | :-- | :-- |
| Dades Crítiques | Bases de Dades de Comptabilitat i Clients | Són essencials per al funcionament diari i canvien sovint |
| Periodicitat (BD) | Cada 4 hores (incremental) + còpia completa diària | Permet recuperar fins a l’última actualització sense perdre més de 4 h |
| Tipus de Còpia (BD) | Incremental + Completa | Redueix temps i espai de còpia |
| Mitjà 1 (Local) | NAS dins de la sala de servidors | Accés ràpid per a recuperacions menors |
| Mitjà 2 (Extern) | Cloud (Google Cloud) | Garantia d’una còpia fora de lloc, segura i automàtica |


***

### Fase 3: Treball en grup

1. Debat i selecció
Després de compartir les propostes, hem coincidit que el NAS local i el núvol són la millor combinació qualitat-preu. Les cintes LTO serien més segures a llarg termini, però massa cares per l’empresa.
2. Política final de còpies de seguretat

#### Dades objecte de còpia

- Servidor:
    - Comptabilitat i Clients (crítiques): còpia incremental cada 4 h, completa cada dia.
    - Projectes i plànols (no crítiques): còpia diferencial diària i completa setmanal.
- Equips clients: només els documents importants de cada tècnic (sincronitzats un cop al dia amb el servidor).


#### Cronograma setmanal detallat

| Dia | Dades | Tipus de còpia | Mitjà |
| :-- | :-- | :-- | :-- |
| Dilluns | BD i Documents crítics | Completa | NAS |
| Dimarts | BD | Incremental | NAS |
| Dimecres | BD i Documents | Diferencial | NAS |
| Dijous | BD | Incremental | NAS |
| Divendres | BD i Documents | Diferencial | NAS |
| Dissabte | BD | Incremental | Cloud |
| Diumenge | Tot (completa) | Completa | Cloud |

#### Elecció de mitjans i ubicació (regla 3-2-1)

- Mitjà 1 (Local): NAS intern amb discs redundants.
- Mitjà 2 (Extern): Còpia automàtica al núvol (Google Cloud).
- Ubicació fora de lloc: còpia al núvol gestionada pel responsable de seguretat.


#### Estratègia de recuperació (RTO/RPO)

- RTO (Temps de recuperació): Les còpies al NAS permeten restablir bases de dades en menys de 4 h.
- RPO (Pèrdua màxima de dades): Còpies incrementals cada 4 h asseguren una pèrdua màxima de només aquest marge.




