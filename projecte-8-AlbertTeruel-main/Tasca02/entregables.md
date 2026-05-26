# Tasca 02. Pla de sostenibilitat

#### Albert Teruel, Joel Dominguez i Lluis Garcia
 
### Fase 1: Diagnòstic i Auditoria

* 20 PCs (2018): Estat crític. La manca de RAM satura el disc dur mecànic. El sobreescalfament indica fallada de dissipació, disparant el consum elèctric. Veredicte: Intervenció tèrmica immediata i actualització.
* Servidor Físic: Ineficient. Sobredimensionat per a un coworking; operativitat 24/7 injustificada. *Veredicte: Desmantellament.*
* Magatzem: Caòtic. Maquinari obsolet inactiu generant risc tòxic. *Veredicte: Evacuació RAEE.*

---

### Fase 2: Solucions

1. Discos SSD SATA III: Eliminen el coll d'ampolla mecànic i redueixen dràsticament el consum d'energia en lectura/escriptura.
2. Ampliació RAM (8GB DDR4): Elimina l'ús del disc com a memòria virtual, reduint els cicles inútils de la CPU.
3. Renovació Tèrmica: Neteja de ventiladors i canvi de pasta tèrmica. Obligatori per frenar el sobreescalfament i el consum base dels ventiladors.
4. Substitució del Servidor per NAS: Un NAS (Energy Star) redueix el consum operatiu de ~300W a menys de ~40W.

---

### Fase 3: Guia de Bones Pràctiques Digitals

[Infografia](Infografia.png)

---

### Fase 4: El Pla de Sostenibilitat Integral

1. Full de ruta de millora

Termini curt:

* Aturada immediata del servidor físic fora de l'horari laboral per tallar el malbaratament d'energia.
* Evacuació incondicional del magatzem per eliminar riscos tòxics.
* Intervenció tèrmica: Neteja física i substitució de pasta tèrmica a les 20 CPUs. Permetre l'estrès tèrmic és una ineficiència inacceptable.

Termini mitjà:

* Clonació de discos HDD a SSD SATA III.
* Instal·lació de la nova memòria RAM en tots els equips de sobretaula.
* Implementació de polítiques de xarxa per bloquejar l'accés de l'usuari a les opcions d'energia. L'apagament remot és obligatori, no opcional.

Termini llarg:

* Migració de dades i desconnexió definitiva del servidor físic.
* Posada en marxa del sistema NAS de baix consum.
* Auditoria de consum elèctric final per validar la caiguda objectiva del 20% en la facturació.

---

2. Protocol de gestió de residus (Normativa RAEE)

* Tolerància zero a l'acumulació: Es prohibeix utilitzar l'espai físic com a abocador de components tecnològics inútils.
* Classificació selectiva: Separació rigorosa de components. Els monitors antics s'han de separar del coure pur o les plaques base.
* Destrucció de dades: Tot disc dur HDD substituït serà sotmès a esborrat criptogràfic o destrucció mecànica abans de sortir de l'edifici. Les filtracions són inadmissibles.
* Traçabilitat i certificació: La transferència de ferralla electrònica només es realitzarà a gestors autoritzats. Sense el certificat oficial de destrucció, l'esforç no té validesa legal i el segell de sostenibilitat queda invalidat.

---

3. Càlcul i Monitoratge de KPIs

PUE (Power Usage Effectiveness):

* Anàlisi crítica: Exigir aquesta mètrica en oficines demostra falta de rigor tècnic. És un indicador dissenyat per a centres de dades.
* Procediment d'aïllament: S'han d'instal·lar mesuradors de consum individuals als PCs per no distorsionar la dada amb la il·luminació o el clima de les persones.
* Fórmula: Consum d'energia total de la instal·lació dividit pel consum exclusiu dels equips informàtics.
* Objectiu: Reduir la ineficiència actual cap a un valor de 1.5.

Taxa de Reutilització de Hardware:

* Fórmula: Maquinari aprofitat dividit pel total de maquinari inicial, multiplicat per 100.
* Justificació: Renovar els components crítics en 20 ordinadors existents és la base de l'eficiència mecànica; comprar equips nous és un malbaratament injustificable.
* Objectiu: Retenir un 90% de l'estructura original. Només es descarten els colls d'ampolla estructurals com els discos durs mecànics o el servidor sobredimensionat.
