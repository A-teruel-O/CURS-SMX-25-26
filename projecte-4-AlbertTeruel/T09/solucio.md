## Fase 1: Preparació de l'entorn

Creem dues màquines virtuals:
- Servidor: Ubuntu Server
- Client: Zorin OS 

Configurem dos adaptadors de xarxa NAT i Host-only.

Apliquem actualitzacions:
```
sudo apt update
sudo apt upgrade -y
```

Comprovem connexió entre equips amb un ping a google i a l'altre màquina


![](img/1.png)

---

## Fase 2: Preparació del servidor

### Creació de grups

L’empresa té dos grups developers i administradors, creem aquests grups amb les següents comandes:

```
sudo groupadd -g 1050 devs
sudo groupadd -g 1051 admins
```

### Creació d'usuaris

Creem comptes d’usuari i li posem la contrasenya amb:

```
sudo useradd -m -u 1052 -g devs dev01
sudo passwd dev01

sudo useradd -m -u 1053 -g admins admin01
sudo passwd admin01
```

![](img/2.png)

### Directoris compartits NFS

Creem els directoris amb:

```bash
sudo mkdir -p /srv/nfs/dev_projects
sudo mkdir -p /srv/nfs/admin_tools
```

### Permisos

Apliquem permisos els grups corresponents:

```bash
sudo chown root:devs /srv/nfs/dev_projects
sudo chmod 2770 /srv/nfs/dev_projects

sudo chown root:admins /srv/nfs/admin_tools
sudo chmod 2770 /srv/nfs/admin_tools
```
![](img/3.png)

### Instal·lació del servidor NFS

Instal·lem NFS:

```bash
sudo apt install nfs-kernel-server -y
```

### Configuració inicial exportacions

Dintre de /etc/exports posem:
```bash
/srv/nfs/admin_tools 192.168.56.0/24(rw,sync)
/srv/nfs/dev_projects 192.168.56.0/24(rw,sync)
```

```bash
sudo exportfs -ra
sudo systemctl restart nfs-kernel-server
```

Replicar usuaris i grups al client per tenir mateix UID/GID.

![](img/4.png)

---

## Fase 3: L'exportació d'Administració

Instalem nfs:
```bash
sudo apt install nfs-common -y
```

### Prova 1: Error típic (root_squash)

Muntem recurs al client:

```bash
sudo mkdir -p /mnt/admin_tools
sudo mount 192.168.56.102:/srv/nfs/admin_tools /mnt/admin_tools
```

Com a root:

```bash
sudo touch /mnt/admin_tools/prova.txt
```

Propietari apareix com **nobody** → *root_squash*

![](img/5.png)

---

### Prova 2: Solució (no_root_squash)

Editem `/etc/exports`:

```bash
/srv/nfs/admin_tools 192.168.56.0/24(rw,sync,no_root_squash)
```

```bash
sudo exportfs -ra
sudo systemctl restart nfs-kernel-server
```

Muntem de nou i creem:

```bash
sudo touch /mnt/admin_tools/prova2.txt
```

Propietari ara és **root**

![](img/6.png)

---

## Fase 4: Exportació de Desenvolupament

Configuració exportació a /etc/exports:

```bash
/srv/nfs/dev_projects 192.168.56.0/24(rw,sync) 192.168.56.105(ro,sync)
```

Muntem al client:

```bash
sudo mkdir -p /mnt/dev_projects
sudo mount 192.168.56.102:/srv/nfs/dev_projects /mnt/dev_projects
```

#### Test usuari dev01 (ha de funcionar)

```bash
su - dev01
touch /mnt/dev_projects/fitxer1.txt
```

![](img/7.png)

#### Canviem IP a 192.168.56.105 → només lectura

![](img/8.png)

Intent d’escriptura → error

![](img/9.png)

#### Usuari admin01 → tampoc pot escriure (no és grup devs)

![](img/10.png)

---

## Fase 5: Muntatge automàtic – /etc/fstab

Afegim a /etc/fstab al client:

```bash
192.168.56.102:/srv/nfs/admin_tools /mnt/admin_tools  nfs  defaults,_netdev  0  0
192.168.56.102:/srv/nfs/dev_projects /mnt/dev_projects nfs  defaults,_netdev  0  0
```

Provem:

```bash
sudo mount -a
```

![](img/11.png)

Reinici i comprovació:

![](img/12.png)

---

[Torna al README](README.md)

[![Tornar al Projecte 4](https://img.shields.io/badge/Tornar_al_Projecte_4-0066cc.svg)](../README.md)

[![Tornar al README General](https://img.shields.io/badge/Tornar_al_README_General-4a5568.svg)](../../README.md)