# P02: Màquina virtual Ubuntu Server 

### Breu descripció

Aquest curs hi treballarem sovint amb servidors i en aquest sector, **Linux** és força predominant, sobretot si parlem de serveis de xarxa. Per això, en aquest primer projecte crearem una màquina virtual Linux, que ens haurà de servir com a base per la resta del curs.

Tot i que per practicar crearem de tant en tant servidors des de zero, és una bona idea disposar d’una **OVA** que ens serveixi per desplegar ràpidament, sense perdre temps en les configuracions inicials. De fet, la virtualització va permetre canviar la forma en la que es treballa en el món de l’administració de servidors.

**Què caldrà fer?** Caldrà que creeu una VM **Ubuntu Server** usant la versió **LTS** més nova. Aquesta màquina haurà de seguir estrictament els requeriments especificats; en cas contrari, l’avaluació serà negativa. És el primer pas per convertir-vos en superherois dels sistemes.

Un cop tingueu la màquina creada i correctament avaluada, fareu una **OVA** per tal de poder crear una VM ràpidament.

---

### Requisits de la Màquina Virtual

* **Recursos de Hardware:** 4 GB RAM i 20 GB de disc.
* **Xarxa (2 adaptadors):**
  * Adaptador 1: Xarxa NAT.
  * Adaptador 2: Pont amb IP `192.168.c.x/24`
    * `c=2` (per a 2n A) o `c=4` (per a 2n B)
    * `x` = número de llista.
* **Credencials d'accés:** Usuari inicial i password: `usuari` / `usuari` (estricte, no es permet cap altre).
* **Serveis:** Instal·lar el servei **SSH**.

---

### Documentació i Guia

A més, fareu una **guia de la instal·lació** on caldrà que documenteu correctament les diverses accions i configuracions. Documentar és bàsic per evitar errors en posteriors instal·lacions. 

El lema d’aquest curs és:
> “Documentar, documentar i documentar”

## Enllaç al Entregable
[P02: Màquina virtual Ubuntu Server](InstalacionUbuntu.pdf)