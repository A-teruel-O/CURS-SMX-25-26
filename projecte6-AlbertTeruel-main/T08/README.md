# T08: Vigilància i auditoria de sistemes

## Breu descripció

### Introducció

Un cop la infraestructura bàsica de **TransLògic S.A.** està operativa, la direcció de l'empresa ha expressat la seva preocupació per la **integritat de les dades** i la **possibilitat d'intrusions no detectades**. En el món de la logística, la informació és tan crítica com la mercaderia física.

Com a consultors de confiança, se us ha encarregat una nova tasca crítica: **establir mecanismes de vigilància activa**.
L'objectiu no és només assegurar que el servidor té prou recursos per treballar, sinó també **configurar les "caixes negres" del sistema (els logs)** per poder rastrejar qualsevol activitat sospitosa o intent d'accés no autoritzat.

***

## Descripció de l'activitat

### 1. Monitorització de Recursos

El client vol assegurar-se que el nou servidor dimensionat suporta la càrrega de treball.

- Accediu al **Monitor de Rendiment** o al **Gestor de Tasques** del servidor.
- Realitzeu una **captura** on es vegi clarament l'estat actual de la **CPU** i la **memòria RAM** disponible.
- Interpreteu breument les dades:
*El servidor està saturat o treballa sense estrès?*

***

### 2. Configuració d'Auditoria de Seguretat

Per detectar possibles **atacs de força bruta** (intents d’endevinar contrasenyes), heu d’activar el **registre d’accessos**.

- Configureu la **política d’auditoria** (via **GPO** o política local del servidor) per auditar els successos d’inici de sessió.
- És imprescindible que activeu tant els **èxits** (per saber qui entra) com els **fracassos** (per saber qui intenta entrar sense permís).

***

### 3. Simulació d’Incidents (Hacking Ètic)

Ara posareu a prova el sistema que acabeu de configurar.

- Tanqueu la sessió actual.
- Intenteu iniciar sessió amb un **usuari existent** (p. ex.: un usuari de magatzem), però introduint la **contrasenya incorrecta** expressament.
- Repetiu aquest procés **3 o 4 vegades seguides**.
- Finalment, inicieu sessió correctament amb l’**administrador**.

***

### 4. Anàlisi Forense (Event Viewer)

Actueu com a pèrits informàtics per trobar les proves de l'intent d'intrusió anterior.

- Obriu el **Visor d’Esdeveniments (Event Viewer)**.
- Aneu al **registre de Seguretat**.
- Busqueu els **esdeveniments recents** que corresponguin als vostres intents fallits.
- Feu clic en un dels esdeveniments i mostreu-ne els detalls
*(usuari que ho ha intentat, hora, IP d’origen si n’hi ha)*.

**Tasca d’investigació:**
Localitzeu l’**Event ID** (identificador de l’esdeveniment) que correspon a un *"intent d’inici de sessió fallit"*.

***

## Què cal lliurar

### Informe d’Auditoria

- Captura dels **recursos del sistema** amb la vostra interpretació.
- Captura de la **configuració de la política d’auditoria** activada.
- **Evidència forense:** captura clara del **Visor d’Esdeveniments** on es vegin els errors d’inici de sessió generats durant la simulació.
- **Resposta tècnica:** indiqueu quin és el número d’**Event ID** que **Windows** assigna als errors d’inici de sessió.

***
