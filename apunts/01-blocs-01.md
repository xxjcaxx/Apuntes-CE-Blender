# Començant a modelar amb blocs

## Configuració inicial de Blender

Instal·lar els plugins:

* Mesh: LoopTools

Configurar en System > Undo Steps a 256 per poder tornar enrere fàcilment.

Instal·lem també Pureref per veure per damunt sempre les imatges de referència. 

## Detecció de les figures geomètriques bàsiques

En la secció de blocking anem a fer un model que pot servir com a "prop" en un videojoc.
Li he demanat a una IA que genere una ruina futurista i m'ha generat una imatge que pot servir d'inspiració:
![inicial](imgs/dalleinicial.png "Imatge Inicial")

Podria ser un portal entre estrelles abandonat per una antiga civilització.

Deguem observar les geometries bàsiques. Per exemple, la part de baix pot ser un tronc de piràmide, la par de dalt són alguns anells connectats per rectangles. En la base es poden intuir unes escales per pujar als anells. 

![esquema](imgs/esquema.png "Esquema geometria")

## Modelat del blocs

En aquesta part es tracta de fer les formes geomètriques bàsiques amb pocs polígons. Sempre tractarem de fer polígons de **4 costats**. En un videojoc no podem tindre triangles o "n-gons", que són polígons de molts costats. 
Per una altra banda, sempre modelarem a **escala real**. Encara que siga una videojoc, els efectes de llums, textures i partícules estan dissenyats a escala per respectar la física. Al redimensionar qualsevol figura, deguem d'aplicar l'escala per a que estiga sempre a 1 amb **Ctrl+A**. 

### El tronc de piràmide

Aquesta és la figura més simple. Després de esborrar tot, afegim un cub amb **Shift+A Mesh > Cube**. En el menú de creació i posteriorment en el menú de ítem, podem aplicar les dimensions aproximades en metres que considerem que té. Suposem que el cercle és de uns 4 metres de diàmetre, així que la base sembla tindre un 2 metres d'alt i uns 6 d'ample.

Recordem aplicar l'escala i entrem al mode Edició amb **Tab**. Ahí seleccionem la cara de dalt pressionant tecla **2** per seleccionar per cares. Una vegada seleccionada, la podem reduir amb **S** per crear la part de dalt del tronc. 3

![tronc](imgs/redimensionartronc.gif "Redimensionar la part de dalt")

Podem jugar amb les dimensions en el mode edició el que necessitem. Per veure cóm queda en vista frontal, podem pressionar **1** en el teclat numèric. Els altres números mostres altres vistes. 

Anem a crear les escales. Com que afecten sols a una part, podem extrudir en l'eix Y amb **E, Y** per tindre més polígons en eixe costat. 

![estrusio](imgs/extrusioescales.gif "Estrusió per a les escales")

Podem llevar les cares de la part de baix del model, ja que no es veuen en el joc.

Per poder modelar l'escala sense afectar a la resta del tronc, podem separar-la amb **P**, eixir del mode edició i tornar a entrar amb l'objecte separat. Més endavant el podem tornar a juntar.

![p](imgs/separarenP.gif "Separar amb P")

Una vegada en el troç separat en mode edició, podem fer **Ctrl+R** per crear nous "edges" en la geometria, tant en vertical com en horitzontal. El separarem en vertical, separem de nou l'objecte en **P** i Separem el del mig en horitzontal

Amb **Shift+Alt** Seleccionem un bucle sencer de vores. i el podem redimensionar en l'eix X amb **R, X**.

![r](imgs/separarenR.gif "Separar amb R")

Per fer els escalons, seleccionem totes les línies creades en **Ctrl+R** i apliquem en el botó dret **Bevel Edges**. Després, seleccionem una de cada nova vora creada i la desplacem abaix. Podem anar canviant de vistes per deixar-ho al nostre gust. Després es pot ajustar de nou.

![escalons](imgs/escalons.gif "Creació dels escalons")

Ara amb **Ctrl+J** Fusionem en mode Objecte totes les geometries. Per anar al detall, podem pressionar **.** En el teclar numèric i s'apropa al vertex seleccionat. Per pegar vertex, entrarem al menú de la tecla **M** després de seleccionar els dos vertex. 

![fusionar vertex](imgs/fusionarvertex.gif "Fusionar vertex")

Seleccionant les vores i amb **F** Podem omplir les cares que falten. Es creen triàngles, però no passa res.

Després de varies operacions com les anteriors, he unit totes les cares, vores i vertex. També hem eliminat vores innecessàries o creat les que calen per millorar la geometria. Amb **Supr** i **Disolve Edges** eliminem els que vulguem sense eliminar les cares.
En la captura encara queda una cara problemàtica, ja que la de dalt té més de 4 vores. Ja l'arreglarem. 

![escales millorades](imgs/escalesacabades.png "Millores geomètriques en les escales")


