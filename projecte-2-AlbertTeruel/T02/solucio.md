# Selecció de SAI per TecnoGestió S.L.

---

## 1. Inventari d'Equips

### Equips que es connectaran al SAI

| Equip | Quantitat | Potència Unitària | Potència Total | Justificació |
|--------|------------|------------------|----------------|---------------|
| Ordinador Sobretaula Epical-Q | 4 | 150W | 600W | Equips crítics que necessiten apagat segur |
| Monitor Samsung Essential S24C330GAU | 4 | 25W | 100W | Permeten visualitzar el procés d'apagat |
| Router AX1800 | 1 | 15W | 15W | Manté connectivitat durant l'apagat |

**Ordinador:**  
[https://www.pccomponentes.com/ordenador-sobremesa-epical-q-soho201-intel-core-i5-12400-16gb-1tb-ssd-nvme](https://www.pccomponentes.com/ordenador-sobremesa-epical-q-soho201-intel-core-i5-12400-16gb-1tb-ssd-nvme)

**Monitor:**  
[https://www.pccomponentes.com/monitor-samsung-essential-s24c330gau-24-led-ips-fullhd-100hz-freesync](https://www.pccomponentes.com/monitor-samsung-essential-s24c330gau-24-led-ips-fullhd-100hz-freesync)

**Router:**  
[https://www.tp-link.com/es/home-networking/wifi-router/archer-ax20/](https://www.tp-link.com/es/home-networking/wifi-router/archer-ax20/)

**Potència total a protegir:** 715W

### Equips que NO es connectaran al SAI

- **Impressora-fotocopiadora multifunció làser (300W):**  
  Les impressores làser tenen becs de consum molt alts en arrencar (fins a 800W) que poden sobrecarregar el SAI. Els fabricants com APC recomanen usar un protector de sobretensions independent per a aquests equips.

---

## 2. Càlcul de Potència Total

**Conversió a VA:**

- Potència en W: 715W  
- Factor de potència: 0.8 (típic equips informàtics)  
- **Potència en VA:** 894 VA  

**Aplicació del marge de seguretat:**

- Potència calculada: 894 VA  
- Marge de seguretat: 20%  
- **Potència mínima SAI necessària:** 1072 VA  

---

## 3. Determinació de l'Autonomia

**Temps mínim requerit:** 10 minuts (suficient per guardar treballs i apagar correctament)

**Fórmula utilitzada:**


On:
- **N** = nombre de bateries  
- **V** = voltatge de bateria (12V típic)  
- **Ah** = amperes-hora de la bateria  
- **Eficiència** = 95%  

---

## 4. Investigació de Models SAI

### Model 1: Tecnoware Era Plus 1500
- **Potència:** 1500 VA / 1050 W  
- **Tipus:** Línia interactiva amb AVR  
- **Preu:** 109€  
- **Sortides:** 2 sortides Schuko  
- **Autonomia benvolguda:** 19.6 minuts  
- **Avantatges:** Preu molt competitiu, compleix requisits  
- **Desavantatges:** Solament 2 sortides, marca menys coneguda  

### Model 2: APC Back-UPS Pro BR1500GI
- **Potència:** 1500 VA / 865 W  
- **Tipus:** Línia interactiva amb AVR  
- **Preu:** 549€  
- **Sortides:** 10 sortides AC  
- **Autonomia benvolguda:** 19.6 minuts  
- **Avantatges:** Marca reconeguda, moltes sortides, pantalla LCD  
- **Desavantatges:** Preu elevat  

### Model 3: Riello NetPower NPW2000
- **Potència:** 2000 VA / 1200 W  
- **Tipus:** Línia interactiva amb AVR  
- **Preu:** 289€  
- **Sortides:** 4 sortides IEC + cables  
- **Autonomia benvolguda:** 26.1 minuts  
- **Avantatges:** Millor relació qualitat-preu, major autonomia  
- **Desavantatges:** Necessita cables IEC–Schuko  

---

## 5. Comparació de Característiques

| Característica | Tecnoware Era Plus | APC Back-UPS Pro | Riello NPW2000 |
|----------------|--------------------|------------------|----------------|
| Compleix requisits | ✓ | ✓ | ✓ |
| Marge de potència | 39.9% | 39.9% | 86.6% |
| Relació qualitat-preu | ★★★ | ★ | ★★★★ |
| Facilitat connexió | ★★★ | ★★★★ | ★★ |
| Marca reconeguda | ★ | ★★★★ | ★★★ |

---

## 6. Justificació de la Selecció Final

**Recomanació:** *Riello NetPower NPW2000*

![Font d'alimentació](img/font.png)

**Motius de la selecció:**
1. Potència suficient: 2000 VA amb marge del 86.6% permet futures ampliacions  
2. Autonomia superior: 26.1 minuts (més del doble del mínim requerit)  
3. Preu competitiu: 289€ – equilibri perfecte entre prestacions i cost  
4. Marca fiable: Riello és reconegut en el sector de SAIs professionals  
5. Tecnologia adequada: Línia interactiva amb AVR, perfecta per a oficines  

**Cost total benvolgut:**
- SAI Riello NPW2000: 289€  
- Protector sobretensions per a impressora: 25€  
- Cables addicionals (si necessari): 15€  
- **Total: 329€**

---

## Conclusions

El **SAI Riello NetPower NPW2000** és l'opció més adequada per TecnoGestió S.L. per la seva excel·lent relació qualitat-preu i capacitat de creixement futur.  
L'autonomia de 26 minuts garanteix temps suficient per completar treballs i realitzar un apagat segur de tots els equips.  

La decisió de no connectar la impressora làser al SAI és tècnicament correcta i econòmicament eficient, seguint les recomanacions dels fabricants capdavanters del sector.


[Torna](../)
