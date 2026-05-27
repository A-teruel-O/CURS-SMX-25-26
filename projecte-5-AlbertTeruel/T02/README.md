## Evolució del Flux de Treball: De la Web al Local

Fins ara hem gestionat el control de versions directament des de la **interfície web de GitHub**. Tot i que ens ha servit per començar, aquesta metodologia presenta limitacions clares que frenen la productivitat:

* **Lentitud d'edició:** L'editor web no és tan versàtil com un entorn local professional (**Visual Studio Code**) o un editor de Markdown específic (**Ghostwriter**).
* **Gestió feixuga:** Administrar fitxers i carpetes des del navegador és ineficient i requereix massa accions manuals.

---

### El Món Real: Git + GitHub

A partir d'ara, treballarem combinant el control de versions local (**Git**) amb un gestor de repositoris remots (**GitHub**). 

> **Nota històrica:** Git va ser creat per **Linus Torvalds** (el creador de Linux). Va néixer com un protocol descentralitzat que va revolucionar el control de versions, substituint els sistemes centralitzats antics. Tot i que fem servir GitHub, existeixen moltes alternatives com **Bitbucket** o **GitLab**.

---

### Com treballarem? (El Flux de Treball)

El procediment es basa a mantenir una còpia sincronitzada entre el núvol i el teu ordinador:

1.  **Sincronització inicial:** Partim d'un repositori a GitHub i en fem una còpia (clon) al disc local del PC.
2.  **Cicle de treball local:** Els canvis es fan sempre en local seguint aquests passos:
    * `add`: Seleccionem els canvis que volem incloure.
    * `commit`: Confirmem els canvis amb un missatge descriptiu.
3.  **Pujar la feina (`push`):** Cada cop que acabem una sessió, pugem els canvis al servidor remot de GitHub.
4.  **Baixar actualitzacions (`pull`):** Abans de començar a treballar, baixem els canvis. Això és **imprescindible** si canvies d'ordinador (per exemple, de casa a l'escola) per evitar conflictes.

