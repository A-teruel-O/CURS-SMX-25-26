# T04: Informe d’Implementació del Servidor d’Impressió

## Fase 1: Preparació de l’Entorn i Maquinari Virtual

### Instal·lació de PDF24
Instal·la el programari al Windows Server per simular les impressores físiques.

### Configuració d'instàncies
Crea dues instàncies independents.

### Nomenclatura corporativa
Vés a Control Panel > Devices and Printers i reanomena les instàncies exactament com:
- IMP_MAGATZEM_A
- IMP_MAGATZEM_B

<img width="939" height="658" alt="image" src="https://github.com/user-attachments/assets/bdc91c1d-39bb-488e-968b-d494898818cb" />

## Fase 2: Instal·lació del rol i configuració del pool

### 1. Instal·lació del rol
- Obre el Server Manager.
- Ves a Add Roles and Features.
- Selecciona Print and Document Services.
- A Role Services, marca únicament Print Server.

<img width="642" height="395" alt="image" src="https://github.com/user-attachments/assets/7adc46dc-60e9-4caf-b233-2ba2f25d6429" />

### 2. Configuració de la cua compartida (Pooling)

- Obre la consola Print Management (printmanagement.msc).
- Navega fins a Print Servers > FL22 > Printers.
- Fes clic dret sobre IMP_MAGATZEM_A > Properties.
- Pestanya Ports
- Marca la casella Enable printer pooling.
- Selecciona el port on es troba IMP_MAGATZEM_A i el port de IMP_MAGATZEM_B.

<img width="816" height="671" alt="image" src="https://github.com/user-attachments/assets/d8d52dee-7b16-44e4-b9dd-a26c8b059074" />

## Fase 3: Desplegament automatitzat via GPO

### Creació de la GPO
- Obre Group Policy Management.
- Crea un nou objecte anomenat GPO_Impressores_Magatzem.
- A la consola Print Management, fes clic dret sobre l'impressora compartida.
- Tria Deploy with Group Policy...
- Busca i selecciona la GPO acabada de crear.
- Marca:
  - The users to whom this GPO applies (per user).
  - The computers to whom this GPO applies (per machine).

<img width="818" height="558" alt="image" src="https://github.com/user-attachments/assets/fcb0903b-e0a1-44ac-b170-ed85307d13e0" />

### Actualització al client
- Al client Windows 11, executa gpupdate /force des d'un CMD amb privilegis.
- Verifica l'aparició del recurs a Settings > Bluetooth & devices > Printers & scanners.

## Fase 4: Seguretat i prova de càrrega

### 1. Restriccions horàries
Per evitar l'ús no autoritzat fora de la jornada de magatzem:

- A les propietats de l'impressora, ves a la pestanya Advanced.
- Selecciona Available from i configura l'interval: 06:00 a 22:00.

<img width="654" height="624" alt="image" src="https://github.com/user-attachments/assets/17eda22f-d63a-4cd1-95a9-c04827c4ac35" />

### 2. Auditoria de balanceig
Executa la prova de càrrega per validar la ininterrupció:

- Envia 10 documents PDF de prova de forma consecutiva.

<img width="929" height="641" alt="image" src="https://github.com/user-attachments/assets/191a9fad-713f-4478-9d7d-f113945178e4" />

- Obre la cua d'impressió i observa com el servidor distribueix els treballs entre els dos ports virtuals seleccionats al pool.

<img width="765" height="517" alt="image" src="https://github.com/user-attachments/assets/304ec329-cb87-461f-b6a1-13d9baf0751e" />

