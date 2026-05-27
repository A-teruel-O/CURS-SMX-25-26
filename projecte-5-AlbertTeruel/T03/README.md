# T03: Serveis de transferència de fitxers

## Introducció a la tasca
Després de la vostra experiència a **EverPia** configurant serveis crítics com DHCP, DNS i administració remota, és hora d'ampliar el vostre horitzó tècnic. 

Encara que serveis *cloud* com Dropbox o Google Drive són habituals, dominar els **protocols fonamentals de transferència** és essencial per a qualsevol administrador de sistemes. Aquesta formació us convertirà en experts en el moviment segur de dades.

---

## Objectius de la formació
En acabar aquesta unitat, sereu capaços de respondre i implementar solucions reals sobre:

* **Funcionament del protocol FTP.**
* **Diferències tècniques:** Mode actiu vs. Mode passiu.
* **Seguretat:** Implementació de servidors FTP segurs.
* **Alternatives modernes:** Ús del protocol **sFTP** sobre SSH.
* **Control d'accés:** Engabiat d'usuaris (*chroot*) en connexions SFTP.
* **Mètodes alternatius** de transferència de fitxers.

---

## Pla de Treball
La formació es divideix en dues fases progressives:

### 1. Fonaments Teòrics i Seguretat
Estudi conceptual dels protocols FTP i sFTP. Analitzarem el trànsit de xarxa per entendre com viatgen les dades i com protegir-les mitjançant l'engabiat d'usuaris.

### 2. Laboratori Pràctic (The "Real World")
Treballarem directament sobre màquines virtuals en dos escenaris:

* **Activitat A - Servidor FTP:** Configuració d'un servidor estàndard, gestió d'usuaris i permisos. Observarem com les dades viatgen "en clar" (sense xifrar).
* **Activitat B - Servidor sFTP (Secure FTP):** Implementació de transferència xifrada sobre SSH i configuració de seguretat avançada per evitar fuites de dades.

> [!IMPORTANT]
> **La seguretat no és una opció, és una obligació.** Com a administradors, entendre la diferència entre protocols xifrats i no xifrats és vital per al vostre futur professional.

---

## Sistema d'Avaluació
La nota final es calcularà segons els següents pesos:

| Tipus de Prova | Descripció | Pes |
| :--- | :--- | :--- |
| **Prova Escrita** | Preguntes sobre protocols, ports, modes i teoria de seguretat. | **40%** |
| **Examen Pràctic** | Repte cronometrat: aixecar servidors FTP/sFTP des de zero. | **60%** |

---

[Tasca](ServidorFTPiServidorsFTP-AlbertTeruel.pdf)
