# T06: Configuració del domini

## Breu descripció

### Introducció

Un cop tenim ja el nostre domini creat, el següent pas és desplegar el domini, és a dir, crear els diferents objectes que el formen: **grups**, **usuaris**, **màquines**.
Aquí veurem la utilitat d’organitzar els objectes amb **unitats organitzatives (OU)**.

## Procediment pràctic

1. **Crear una estructura d’unitats organitzatives (OU)** coherent i justificar la decisió.
2. **Definir la següent estructura de grups:**
    - `gestio`
    - `magatzem`
    - `gerencia`
    - `personal` (tots els grups anteriors han de ser membres d’aquest grup)
3. **Crear una plantilla d’usuari per cadascun dels grups:**
    - Gestio
    - Magatzem
    - Gerencia
Cada plantilla ha de tenir definida:
    - La pertinença al grup corresponent.
    - La creació de la carpeta personal.
4. **Definir un usuari de prova** per cadascuna de les plantilles.
5. **Aprovisionar un equip** anomenat **PC1** dins la **OU equips**.
6. **Crear una màquina virtual (VM)** amb:
    - **Windows 11**
    - **4 GB de RAM**
    - **Disc dur suficient**
    - Xarxa en **NAT**
7. Un cop creat l’equip, **afegir-lo al domini**.
8. **Comprovar el correcte funcionament**, iniciant sessió a l’equip client amb els tres usuaris de prova.

## Materials i links de suport

- **UD6.AA3 Desplegament** – [Moodle 0224 SOX]

[Guia](guia.md)
