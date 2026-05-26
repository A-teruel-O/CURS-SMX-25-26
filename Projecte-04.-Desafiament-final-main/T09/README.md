Introducció
Molt bé, equip de consultors júniors, en el nostre projecte, ens trobem ara amb un requisit tècnic molt habitual per part dels nostres clients: la  centralització de dades en entorns Linux.

El Cas Client:  DevOptimize Solutions
El nostre client, DevOptimize Solutions, és una petita startup de desenvolupament de programari que treballa exclusivament amb Linux. Tenen un problema crític: el seu codi font i els seus actius (documents de disseny, scripts) estan descontrolats. Cada desenvolupador té còpies locals, cosa que provoca errors de versió constants i una pèrdua d'eficiència brutal.

Ens han contractat per implementar un servidor de fitxers centralitzat. Atès que tot l'entorn és Linux, la solució nativa, més ràpida i eficient del sector és NFS (Network File System).

El client ha insistit en que treballa sense un entorn d’autenticació centralitzada i que, de moment, no té previst fer aquest pas.
Per mostrar al client com quedarà la solució proposada a partir de les seves demandes i poder mostrar també les limitacions, se t’encarrega fer una demostració del sistema.

Crearàs un servidor NFS (NFSv3) i un client Linux que consumeixi els recursos compartits. Hauràs de crear usuaris i grups per simular l'entorn del client i demostrar el control d'accés utilitzant les opcions d'exportació (/etc/exports) i els permisos del sistema de fitxers (chmod, chown).

En aquest repositori tens la descripció de la tasca a realitzar:
https://github.com/SMX2n/Projecte04-NFS

- [Guia](solucio.md)
