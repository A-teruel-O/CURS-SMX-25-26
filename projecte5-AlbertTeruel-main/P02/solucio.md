# Resum per al client

TransLògic necessita renovar el servidor central i triar el tipus de llicència de Windows que li surti millor avui i d’aquí 5–7 anys.

La proposta és clara: Windows Server 2025 Datacenter + llicències per dispositiu, perquè ofereix una tarifa plana de màquines virtuals, control de costos i evita sorpreses econòmiques si l’empresa creix en el futur.

***

## 1. Com funciona la llicència de Windows Server 2025

Windows Server ja no es llicencia “per servidor”, sinó pel nombre de nuclis (cores) que té el maquinari físic.

Per complir les normes de llicenciament, s’han de respectar tres punts:

- S’han de llicenciar tots els nuclis físics del servidor.
- Cada servidor ha de tenir com a mínim una llicència de 16 nuclis (encara que en tingui menys).
- Cada processador ha de tenir com a mínim 8 nuclis llicenciats.


### Sobre les màquines virtuals (VMs)

Edició Standard:

- Amb una llicència que cobreixi tots els nuclis del servidor, es poden crear 2 màquines virtuals.
- Si se’n volen més, cal tornar a llicenciar tots els nuclis del servidor (és a dir, comprar “capes” addicionals de la mateixa llicència).

Edició Datacenter:

- Un cop el servidor està totalment llicenciat per nuclis, es poden crear màquines virtuals il·limitades sense pagar llicències extra.

***

## 2. El cas de TransLògic: 1 servidor, 12 VMs

Situació actual:

- 1 servidor físic amb 24 nuclis (2 CPUs x 12 cores).
- Necessitat de virtualitzar 12 màquines virtuals.


### Opció Standard

Cada “pack complet” de llicència del servidor dóna dret a 2 VMs.
Per arribar a 12 VMs:

$$
12 ÷ 2 = 6 \text{ repeticions de llicència}
$$

Això implica:

- Llicenciar el servidor 6 vegades.
- 24 nuclis × 6 = 144 nuclis llicenciats en total.

Cost aproximat:

- Windows Server 2025 Standard: ~1.000 € per 16 cores.
- 24 cores = 1,5 packs → ~1.500 € per llicència completa.
- 6 repeticions → 1.500 € × 6 = ~9.000 €.


### Opció Datacenter

Només cal llicenciar un cop els 24 nuclis del servidor.

- 24 nuclis llicenciats.
- Màquines virtuals il·limitades.
- Possibilitat de créixer sense cost extra en Windows Server.

Cost aproximat:

- Windows Server 2025 Datacenter: ~6.000 € per 16 cores.
- 24 cores = 1,5 packs → ~9.000 €.


### Resultat econòmic

| Opció | Cost inicial aproximat | VMs incloses | Escalabilitat |
| :-- | :-- | :-- | :-- |
| Standard | ~9.000 € | 12 VMs | Cost alt per cada nova VM |
| Datacenter | ~9.000 € | Il·limitades | Creixement sense cost |

Conclusió econòmica:
El cost inicial és similar, però Datacenter és clarament més rendible a mitjà i llarg termini, ja que qualsevol nova VM no genera cap cost addicional.
Amb Standard, la VM número 13 implicaria tornar a llicenciar tot el servidor. Amb Datacenter, no hi ha cap cost addicional.

***

## 3. Llicències d’accés (CALs): millor per dispositiu

A banda de la llicència del servidor, calen llicències perquè els usuaris o dispositius hi puguin accedir. Hi ha dues opcions:

- User CAL (per usuari): Cada persona té la seva llicència i pot accedir des de diversos dispositius.
- Device CAL (per dispositiu): La llicència va lligada al dispositiu, i diferents persones el poden fer servir.


### Escenari de TransLògic

Oficina:

- 30 persones
- 30 PCs
(1 persona / 1 dispositiu)

Magatzem:

- 15 treballadors
- 5 tauletes compartides en torns


### Comparativa

- User CAL: 30 oficina + 15 magatzem = 45 User CALs
- Device CAL: 30 PCs + 5 tauletes = 35 Device CALs


### Decisió

La millor opció és Device CAL, perquè:

- Cal comprar 10 llicències menys.
- És més econòmic.
- Permet reforços de personal en campanyes sense cost extra.
- Mentre no s’afegeixin nous dispositius, el cost no augmenta.

***

## 4. Consideració important: SQL Server

La VM de SQL Server (Base de dades de l’ERP) no queda coberta per la llicència de Windows Server.
SQL Server té el seu propi model de llicenciament (normalment per nucli) i s’ha de pressupostar de manera independent.

Aquest estudi de costos cobreix exclusivament Windows Server 2025 i les seves CALs d’accés.

***

## 5. Per què Datacenter, si només hi ha un servidor?

Tot i que Datacenter s’associa habitualment a grans entorns o clústers, en aquest cas la decisió és estratègica i econòmica.

Motivos principals:

- TransLògic ja té un volum alt de VMs (12).
- És previsible el creixement futur (nous serveis, proves, aplicacions...).
- Datacenter converteix el servidor en una tarifa plana de màquines virtuals.

Això implica:

- Cost controlat a llarg termini.
- Escalabilitat sense despesa addicional.
- Simplicitat de gestió.
- Reducció del risc en auditories de llicències.
- Possibilitat futura de clúster si s’afegeix un segon servidor.

Encara que avui no es facin servir funcions avançades com Storage Spaces Direct o Software Defined Networking, Datacenter deixa la infraestructura preparada per a alta disponibilitat futura.

***

## Conclusió final

La solució recomanada per a TransLògic S.A. és:

- Windows Server 2025 Datacenter
- Llicències Device CAL
- Llicenciament independent de SQL Server

Aquesta solució ofereix:

- Cost inicial similar a Standard.
- Creixement sense cost en llicències de Windows.
- Control de despesa a llarg termini.
- Simplicitat de gestió.
- Preparació per a futures ampliacions.
- Seguretat davant auditories.
- Infraestructura preparada per evolucionar.

És la solució més segura, escalable i rendible per al present i el futur de TransLògic.


