# Bake amb ArmorPaint

El procés de bake implica prendre dades, com la il·luminació, les ombres, els reflexos o els mapes de desplaçament, i calcular-los i desar-los en una textura. Aquesta textura "bakeada" pot després ser aplicada a un objecte 3D per simular aquests efectes sense necessitat de recalcular-los en temps real durant el renderitzat.

El bake pot ser útil en diverses situacions. Per exemple, en lloc de calcular la il·luminació global en temps real durant el renderitzat, es pot fer un bake de la il·luminació i guardar-la en una textura. Això redueix el temps de renderització en temps real i permet una visualització més ràpida del model. Un altre cas comú és el bake de mapes de desplaçament, que captura els detalls d'alt nivell d'un model i els guarda en una textura per simular la geometria addicional sense augmentar la càrrega computacional.

> En un entorn professional es sol utilitzar **Substance Painter** per texturitzar i fer el bake. No obstant, les regles bàsiques d'aquest procés es poden aprendre amb ferramentes gratuïtes o molt més barates. En el nostre cas, el stack de programes inicials srean Blender, ArmorPaint, Gimp i Krita.

Blender compta amb moltes ferramentes potents per al texturitzat. No obstant, una ferramenta externa ens proporciona major control. Algunes de les característiques són: El seu motor de renderitzat en temps real o les capacitats de pintures i textures amb capes no destructives.

## Resum del procés de bake

El procés per crear una versió de baixa poligonització (low poly) i una versió d'alta poligonització (high poly) per fer un bake pot variar segons les teves necessitats i el flux de treball específic que s'utilitze. Aquesta és una estratègia:

* Modelat del low poly i el high poly segons els documents anteriors.
* Creació del bake de les normals i altres amb blender segons la tècnica del cage per no tindre que aplicar les mateixes UVs al high.
* Exportar les imatges del bake.
* Exportar la versió low per separat en format .obj.
* Importar la versió low en ArmorPaint.
* Importar les imatges per crear una textura que aplicar al low en ArmorPaint.
* Aplicar la textura i pintar sobre el low els detalls de color i textures addicionals.

## Bake en Blender amb Cage

El problema de la versió High dels nostres models és que s'ha aplicar un augment de la geometria i s'han perdut les marques **seam**. Tornar a desplegar les UVs de la mateixa manera serà molt complicat.

> Si es fa la versió High a partir d'un modificador **Subdivision** es pot mantenir les UVs. Això pot ser útil si no volem fer "sculpting". 

Blender permet fer un **bake** amb una **Cage**. Amb aquesta tècnica, seleccionem els dos objectes i li indiquem que calcule el mapa de normals de l'objecte High Poly però per a el desplegament de UVs de l'objecte Low Poly. Com que el Low i el High estan interseccionats en moltes parts, el resultat té molts "glitches". Si construïm una coberta més gran que el High poly amb la mateixa geometria que el Low, s'apliquen les normals sense eixos problemes.

El procés és:

* Fer les UVs correctament del Low. Rectificar si cal les transformacions i l'origen de la geometria dels dos.
* Crear un duplicat del Low i ampliar per les normals amb **Alt+s** en el mode edició.
* Ampliar el duplicat "cage" fins a que cap part del High estiga fora de la coberta.
* Aplicar una textura diferent al Low, que tinga un input **Image Texture** i crear una imatge de la resolució necessària. Enllaçar eixa imatge a les normals en el tipus d'editor **Shader Editor**.
* Seleccionar primer el Low, després el High.
* Triar el motor de render **Cycles**.
* En la pestanya de **Bake**, triar el **bake type** a **"Normal"**. **Selected to active** i dins **Cage** i triar l'objecte que fa de "cage".
* Triar també l'output a **"Image Textures"**. Això provocarà que el render s'aplique a la normal del low.

https://www.youtube.com/watch?v=nJ0PM7m9TJc 

Una vegaga fet el **Bake**. Em el tipus d'editor **Image Editor** podem observar si és correcta respecte a les UVs. També podem exportar la imatge.

El mateix procés el farem per a les **Normals**, **Ambient Occlusion**, **Emit**. 

Amb les imatges exportades és hora de aplicar les textures al Low amb **ArmorPaint**

> Amb Substance Painter es pot importar el model Low Poly i aplicar una técnica anomenada "mesh as high poly mesh" que fa el mateix procés internament. Aplica els UVs de Low al high i permet fer el bake del High en el mateix programa. Amb Armorpaint és un poc més complicar, ja que cal fer el bake del high amb les UVs correctes i després exportar les normals i importar-les com a textura al Low.

## Importació dels models i normals:



En aquest vídeo fa el procés de bake també en ArmorPaint, això és un poc complicat. A partir d'ahí tot és aplicable: https://www.youtube.com/watch?v=Gsq20kQ6ddY 


## Aplicació d'altres modificacions:

## Tornar la textura a blender: