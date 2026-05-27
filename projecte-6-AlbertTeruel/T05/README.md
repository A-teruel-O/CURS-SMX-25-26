# T05: Top Secret — Protegint els secrets

## Breu descripció

### Introducció

Aprofitant que ja esteu treballant amb la seva infraestructura web, des de **Projecte Nexus** us sol·liciten una nova petició d’ajuda.
A causa del gran volum de dades sensibles que gestionen (*dades personals d'estudiants, exàmens oficials no publicats i certificats de notes*), estan molt preocupats per la **integritat** i **privacitat** de la seva gestió acadèmica.

La direcció de Projecte Nexus us ha demanat una **demostració pràctica** de com la vostra empresa pot garantir els tres pilars de la seguretat en la informació:

- **Confidencialitat**
- **Integritat**
- **Autenticitat**

***

## Descripció de l’activitat

### Tasca 1: Protecció de dades en repòs (Xifratge Simètric)

Els caps de departament necessiten transportar els exàmens finals en memòries USB per imprimir-los a secretaria, però temen perdre el dispositiu i que les preguntes es filtrin abans de la data de la prova.

#### Objectiu

Crear un **contenidor xifrat** (unitat virtual) dins d’un pendrive (simulat al disc dur) utilitzant **VeraCrypt** o programari similar.

#### Requisits

- Crear un volum de **100 MB**.
- Utilitzar l'algorisme de xifratge **AES-256**.
- Establir una **contrasenya robusta**.
- Dins la unitat xifrada, copiar un fitxer anomenat **EXAMEN_FINAL_SEGURETAT.txt** amb preguntes de prova.
- Demostrar que, sense muntar la unitat amb la contrasenya, el fitxer és **inaccessible**.

***

### Tasca 2: Verificació d’Integritat (Hashing)

**Nexus** distribueix material didàctic i programari als alumnes a través del seu servidor web. Volen assegurar-se que els fitxers **no han estat alterats** per un atacant.

#### Objectiu

Fer servir una eina de resum criptogràfic per comprovar si un fitxer ha estat modificat.

#### Procediment

1. Crear un document de text anomenat **nota_final_curs.txt** amb el contingut:
> L'alumne ha aprovat amb un 5
2. Calcular el **Hash SHA-256** del fitxer original.
3. Modificar el fitxer canviant una sola xifra (exemple: “9” en lloc de “5”).
4. Tornar a calcular el Hash i comparar els resultats per demostrar que **l’empremta canvia totalment**, revelant la manipulació.

***

## Què cal lliurar

Heu de redactar un **informe tècnic** (en format Markdown) per al client que inclogui:

### 1. Justificació teòrica

Una breu explicació (màxim 10 línies) sobre la diferència entre:

- **Xifratge (Tasca 1):** amaga o protegeix la informació per assegurar la seva **confidencialitat**.
- **Funció hash (Tasca 2):** genera una empremta digital per assegurar la **integritat** de les dades.


### 2. Evidències de la Tasca 1

- Captura de pantalla de la configuració del volum (algorisme escollit).
- Captura de la unitat muntada amb l'examen secret dins.
- Captures que mostrin el procés d’accés al fitxer.


### 3. Evidències de la Tasca 2

- Captura de pantalla del terminal o programa mostrant **els dos hashos** (l’original i el modificat).
Això ha de deixar clar que els valors són completament diferents.


### 4. Conclusió

Redactar una breu recomanació final a **Nexus** sobre:

- La importància de protegir les dades portables amb **xifrat** i gestionar correctament les **contrasenyes** (robustesa, emmagatzematge segur).
- La necessitat d’utilitzar **hashing** per assegurar la **integritat** de documents importants (actes de notes, contractes, informes...).

***

## Material de suport

- **Material de l’assignatura:** *Seguretat Informàtica. RA3. Introducció a la criptografia* — [Moodle de l’assignatura]
- **Tutorial VeraCrypt:** [https://veracrypt.io/en/Beginner's%20Tutorial.html](https://veracrypt.io/en/Beginner's%20Tutorial.html)

***


[Solucio T05: Top Secret](guia.md)
