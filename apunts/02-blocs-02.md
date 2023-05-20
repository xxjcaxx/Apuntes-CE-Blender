# Blocs 2

Recordem L'anterior document en el que Decidíem que la part de dalt serien Cilindres i Rectangles.

![esquema](imgs/esquema.png "Esquema geometria")

Al crear un cilindre és important decidir les vores que va a tindre. Blender ens dona 32 per defecte, però pot ser massa per a un joc. Així que abans de fer res, en el menú de creació, li indicarem que 16 cares.

**Mayus+A Mesh > Cilinder**, triar 16 edges. Després rotar 90 graus amb **R, X, 90** i desplaçar amb **G Z**. El cilindre té uns 4 metres de diàmetre. Li donem les dimensions i apliquem l'escala amb **Ctrl+A**. També pot ser útil **Botó dret > Set Origin > Origin to Geometry**.

> En aquest cas, era millor fer-lo de 32 cares, conservem l'exemple per veure cóm es pot decidir les cares en el moment de la creació. 

![cilindre](imgs/cilindreoriginal.png "Cilindre Original")

La geometria d'un cilindre és problemàtica per a jocs perquè té una cara amb 16 vores (ngon). En aquest cas no será un problema, perquè al fer el toroide es crearan cares de 4 vores. En altres casos, cal tallar manualment o triangular automàticament.

Per crear el toroide podem seleccionar les cares, **I**, eliminar les cares del centre i reconstruir les cares interiors amb **F**.

![toroide](imgs/toroide.gif "creacio del toroide")

També podríem haver crear una circunferencia 2D i extrusionar.

Podem duplicar el toroide amb **Ctrl+D** i redimensionar.

A continuació anem a crear els rectangles. No són regulars i no tenen perquè estar separats dels cilindres, així que unint vores els poden crear

![rectangles](imgs/rectangles.gif "Unió dels rectangles")

Després de crear totes les cares per al rectangles, el modelat en blocs bàsic està completat. En aquest cas no cal cap rectificació de geometria

![cilindre acabat](imgs/cilindreacabat.png "Cilindre Acabat")

> Per a treballar amb més comoditat, podem pressionar **/** per a ocultar la resta d'elements.