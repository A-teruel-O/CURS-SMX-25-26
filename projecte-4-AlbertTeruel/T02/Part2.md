# PART 2: Còpia de seguretat d’un servidor Linux (Ubuntu Server)

## Preparació de l’entorn

- **Màquina virtual** amb **Ubuntu Server**.  
- **Segon disc dur** de **10 GB** afegit a la màquina.  

---

## 1. Inicialitzar, formatar i muntar el disc de backup
- Crear el directori de muntatge:
  ```
  sudo mkdir /media/backup
  ```
- Identificar el nou disc:
  ```
  lsblk
  ```
![](img/11.png)

- Crear el sistema de fitxers **xfs**:
  ```
  sudo mkfs.xfs /dev/sdb
  ```
- Muntar el disc a `/media/backup`:
  ```
  sudo mount /dev/sdb /media/backup
  ```
![](img/12.png)

---

## 2. Instal·lar Duplicity
Instal·lar el programari necessari:
```
sudo apt update
sudo apt install duplicity
```
![](img/13.png)

---

## 3. Crear usuaris i arxius de prova
- Crear dos usuaris nous:
  ```
  sudo adduser usuari1
  sudo adduser usuari2
  ```
- Crear **4 arxius de 10 MB** dins el directori `/home` del teu usuari:
  ```
  fallocate -l 10M arxiu1
  fallocate -l 10M arxiu2
  fallocate -l 10M arxiu3
  fallocate -l 10M arxiu4
  ```
![](img/14.png)

---

## 4. Fer una còpia de seguretat de /home
Executar una còpia completa de la carpeta `/home` com a root:
```
duplicity /home file:///media/backup
```
![](img/15.png)

---

## 5. Esborrar arxius i restaurar la còpia
- Esborrar els arxius creats:
  ```
  rm arxiu*
  ```
- Restaurar la còpia com a root:
  ```
  duplicity restore file:///media/backup /home --force
  ```
- Comprovar que els arxius s’han recuperat correctament.  
![](img/16.png)

---

## 6. Còpia incremental
- Crear un **nou arxiu de 4 MB**:
  ```
  fallocate -l 4M arxiu5
  ```
- Tornar a executar la còpia com a root:
  ```
  duplicity /home file:///media/backup
  ```
- Verificar que la còpia és incremental (confirmem que u es mirant la següent captura).  
![](img/17.png)

---

## 7. Desmuntar la unitat de backup
Desmuntar el disc:
```
sudo umount /media/backup
```
![](img/18.png)

---

# Automatització amb scripts i cron
> La unitat de backup ha d’estar desmuntada per defecte.

---

## 8. Script de còpia completa fullbackup.sh
- Crear l’script:
  ```
  nano fullbackup.sh
  ```
- Contingut bàsic:
  ```
  #!/bin/bash
  export PASSPHRASE=contrasenya
  mount /dev/sdb /media/backup
  duplicity /home file:///media/backup
  umount /media/backup
  ```
- Donar permisos d’execució:
  ```
  chmod +x fullbackup.sh
  ```
![](img/19.png)

---

## 9. Programar la còpia completa amb cron
- Editar el **crontab** com a *root*:
  ```
  sudo crontab -e
  ```
  (opció 1)

- Afegir la línia:
  ```
  0 23 * * 0 /ruta/fullbackup.sh
  ```
![](img/20.png)

---

## 10. Script de còpia incremental-incrementalbackup.sh
- Crear l’script:
  ```
  nano incrementalbackup.sh
  ```
- Contingut:
  ```
  #!/bin/bash
  export PASSPHRASE=contrasenya
  mount /dev/sdb /media/backup
  duplicity incremental /home file:///media/backup
  umount /media/backup
  ```
- Donar permisos:
  ```
  chmod +x incrementalbackup.sh
  ```
![](img/21.png)

---

## 11. Programar la còpia incremental amb cron
Afegir al **crontab**:
```
0 23 * * 1-6 /ruta/incrementalbackup.sh
```
![](img/22.png)


## Conclusió

Còpia completa: diumenge a les 23:00

Còpia incremental: de dilluns a dissabte a les 23:00

La unitat de backup només es munta durant el procés, millorant la seguretat

[Torna al README](README.md)

[![Tornar al Projecte 4](https://img.shields.io/badge/Tornar_al_Projecte_4-0066cc.svg)](../README.md)

[![Tornar al README General](https://img.shields.io/badge/Tornar_al_README_General-4a5568.svg)](../../README.md)