# P01: Planificació i Memòria Tècnica - FoodLogístic S.A.

## 1. Context i Objectius

Aquesta planificació respon a la necessitat de modernitzar la infraestructura de FoodLogístic S.A. en un termini de 15 dies hàbils. L'objectiu és blindar la cadena de fred mitjançant alta disponibilitat d'impressió i garantir la integritat legal de les dades (LOPD-GDD).

## 2. Anàlisi de Tasques i Camí Crític

- Ordre lògic: La T01 és el bloquejant estratègic; sense l'organigrama no hi ha desplegament de l'Active Directory (T03).
- Colls d'ampolla: La T03 (Servidors) és el punt de fallada únic. Si el disseny de permisos NTFS i quotes FSRM s'allarga, es bloqueja la gestió d'impressió (T04) i la documentació final.
- Tasques en paral·lel: Mentre Joel executa la infraestructura base, Albert i Lluís avancen en la identitat digital (T02) i l'estudi Cloud (T07) per optimitzar el calendari.


## 3. Justificació de l'Esforç

S'ha utilitzat un model de càlcul d'hores basat en la complexitat tècnica real descrita a les memòries de cada tasca:


| Tasca | Recerca / Comprensió | Implementació | Proves i Errors | Doc. i Coord. | Total Hores |
| :-- | --: | --: | --: | --: | --: |
| T03: Servidors | 3h | 8h | 4h | 1h | 16h |
| T04: Impressió | 1h | 4h | 2h | 1h | 8h |
| T05: Vídeos LOPD | 3h | 8h | 2h | 2h | 15h |
| T07: Cloud | 2h | 4h | 1h | 1h | 8h |

- T03: L'elevat temps de proves es deu a la validació de les quotes de 500 MB per usuari i el filtratge de fitxers `.exe`.
- T05: L'esforç d'implementació respon a l'edició de dos vídeos formatius que requereixen l'entorn de sistema operatiu per a les captures.


## 4. Diagrama de Gantt

<img width="524" height="402" alt="image" src="https://github.com/user-attachments/assets/30120c99-f7d8-4656-a3e7-9254f36f6580" />

```text
@startgantt
title Planificació del Projecte - FoodLogístics S.A.
language ca
Project starts 2026-05-04
saturday are closed
sunday are closed

' --- Estils ---
skinparam {
ganttChartTitleFontSize 20
taskFontSize 14
taskHeight 30
}

' --- SETMANA 1 (4 a 8 de maig) ---
[T01: Estudi competència] as [T01] lasts 2 days
[T03: Servidors, AD i FSRM] as [T03] lasts 5 days
[T02: Web Corporativa Base] as [T02] lasts 3 days
[T01] starts at 2026-05-04
[T03] starts at 2026-05-04
[T02] starts at [T01]'s end

' --- SETMANA 2 (11 a 15 de maig) ---
[T04: Impressió i GPO] as [T04] lasts 3 days
[T06: Escut Digital LOPD] as [T06] lasts 2 days
[T07: Estudi Migració Cloud] as [T07] lasts 3 days
[T05: Producció Vídeos LOPD] as [T05] lasts 3 days
[T04] starts at [T03]'s end
[T06] starts at [T02]'s end
[T07] starts at 2026-05-11
[T05] starts at [T06]'s end

' --- SETMANA 3 (18 a 22 de maig) ---
[T08: Consens Web Definitiva] as [T08] lasts 1 day
[T09: Memòria Tècnica i Gantt] as [T09] lasts 3 days
[T10: Càlcul de Pressupostos] as [T10] lasts 2 days
[T08] starts at [T06]'s end
[T09] starts at [T07]'s end
[T10] starts at [T09]'s start

' --- Dependències Forçades (Fletxes) ---
[T03] -> [T04]
[T02] -> [T06]
[T08] -> [T09]

' --- Colors per Responsable (RACI) ---
[T01] is colored in LightBlue
[T07] is colored in LightBlue
[T09] is colored in LightBlue
[T10] is colored in LightBlue
[T03] is colored in LightGreen
[T04] is colored in LightGreen
[T02] is colored in LightYellow
[T05] is colored in LightYellow
[T06] is colored in LightYellow
[T08] is colored in LightGray

legend right
| Color | Responsable |
| <#LightBlue> | Albert Teruel (Gestió/Cloud) |
| <#LightGreen> | Joel Dominguez (Sistemes) |
| <#LightYellow> | Lluís García (Web/Suport) |
| <#LightGray> | Tot l'equip (Consens) |
end legend
@endgantt
```


## 5. Matriu de Responsabilitats

| Tasca | Albert | Joel | Lluís |
| :-- | :-- | :-- | :-- |
| T01 (Competència) | R/A | I | C |
| T03 (Sistemes) | C | R/A | I |
| T04 (Impressió) | I | R/A | C |
| T05 (Vídeos LOPD) | C | I | R/A |
| T07 (Cloud) | R/A | C | I |
| T08 (Consens) | A | R | R |

(R: Responsable d'execució, A: Responsable final/Validador, C: Consultat, I: Informat)

## 6. Pla de Contingència i Riscos

| Risc | Impacte | Mesura de resposta |
| :-- | :-- | :-- |
| Retard en T03 (AD/NTFS) | Alt | Aplicació immediata dels 2 dies de buffer final i priorització de les quotes NTFS sobre el filtratge de fitxers. |
| Incompatibilitat GPO (T04) | Mitjà | Ús de punts de restauració (snapshots) abans del desplegament de les polítiques d'impressió. |
| Error en Pressupost Cloud (T07) | Baix | Activació del Pla B (Google Workspace) si les llicències M365 superen el límit de cost per usuari. |

## 7. Reflexió i Decisions Clau

- Tasca crítica: La T03. Sense el controlador de domini i l'organigrama configurat, no es poden aplicar les GPOs d'impressió ni les polítiques d'escut digital web.
- Decisió difícil: S'ha decidit esglaonar l'inici de la T05 a la setmana 2 per garantir que els vídeos formatius mostrin el sistema real ja configurat i auditat.
- Modificació d'estimació: Es va ampliar la T04 de 4 a 8 hores en detectar que la configuració del Printer Pooling sota escenaris d'alta càrrega requeria simulacions d'estrès.
- Pregunta obligatòria (modificació inicial): Hem rectificat el temps de documentació de la T07 en comprovar que la comparativa de preus d'Azure/AWS era més complexa de l'esperat inicialment.
- Marge de millora: Amb una setmana extra, implementaríem un sistema de monitoratge (Zabbix) per preveure fallades en el pool d'impressores abans que s'aturi la logística.
