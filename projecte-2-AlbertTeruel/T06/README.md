# T06: El servei de DHCP: configuració pràctica

### Breu descripció
Ara que ja heu realitzat la formació teòrica, el vostre tutor t'ha assignat una tasca crucial per a un nou projecte amb un client que necessita modernitzar la seva infraestructura de xarxa.

El client té una xarxa interna que actualment assigna les adreces IP de manera manual, cosa que provoca conflictes d'adreces i una gestió ineficient. L'encàrrec és dissenyar i implementar un servidor DHCP per automatitzar aquest procés, millorant la fiabilitat i reduint la càrrega de treball per als administradors de xarxa. El client ha optat per utilitzar un sistema operatiu **Ubuntu Server** per a la tasca.

La teva missió és la següent:

---

### Tasques a realitzar

#### 1. Configuració del Servidor
* **Instal·lació:** Instal·la el paquet necessari per al servidor DHCP en un servidor Ubuntu.
* **Configuració del fitxer principal:** Modifica els paràmetres del servei segons el següent pla de disseny:
  * **Subxarxa:** `192.169.x.0/24` (on *x* correspon al teu número de llista).
  * **Rang d'adreces:** `192.169.x.100` a `192.169.x.200`
  * **Porta d'enllaç (Gateway):** `192.169.x.254`
  * **Servidor DNS:** `8.8.8.8`
* **Desplegament:** Configura el servidor per assignar la porta d'enllaç i el servidor DNS als clients. Reinicia el servei i verifica que s'ha iniciat correctament, sense cap error en els diaris del sistema.

#### 2. Verificació i Proves
* **Client de prova:** Utilitza una màquina client (**Zorin OS**) per connectar-te a la xarxa.
* **Anàlisi de tràfic:** Captura amb **Wireshark** els paquets de la negociació completa (procés DORA) entre el client i el servidor.
* **Validació d'adreçament:** Verifica que el client ha obtingut una adreça IP del servidor DHCP i comprova que l'adreça assignada està estrictament dins del rang definit.
* **Validació de paràmetres de xarxa:** En el client, verifica que la porta d'enllaç i l'adreça del servidor DNS s'han assignat correctament.
* **Configuració de reserva estàtica:** Per verificar el funcionament de la reserva, inclou una entrada específica a la configuració del servidor que associï l'adreça MAC del client de prova a una IP fixa fora del rang dinàmic (per exemple, `192.169.x.80`). Reinicia el servei de xarxa al client i comprova l'aplicació efectiva de la nova adreça reservada.

---

### Requisits de l'Informe Detallat
És obligatori documentar tot el procés en un informe que contingui de forma estructurada:
1. Els passos detallats seguits per a la instal·lació i la configuració del servidor.
2. Les comandes de terminal utilitzades per verificar el correcte funcionament del servei.
3. Captures de pantalla del servidor i del client que mostrin la configuració, els resultats de les proves i els paquets de la negociació capturats.

---

## Enllaç al Entregable
[Informe DHCP](AA2-ServidorDHCP.pdf)

[![Tornar al Projecte 2](https://img.shields.io/badge/Tornar_al_Projecte_2-0066cc.svg)](../README.md)

[![Tornar al README General](https://img.shields.io/badge/Tornar_al_README_General-4a5568.svg)](../../README.md)


