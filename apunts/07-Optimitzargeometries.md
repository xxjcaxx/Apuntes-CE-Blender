# Optimitzar Geometries

Els motors de jocs van a triangular totes les geometries. Les cares de 3 i 4 vores són perfectes per triangular, però els ngons no. Les cares de 3 vores no permeten els loops i dificulten el modelat. Per tant, utilitzarem cares de 4 o quads sempre que es puga i les de 3 per triangular i completar malles.

## Rectificació de la malla

Normalment la triangulació de ngons s'ha de fer manualment abans de passar al motor de jocs. No obstant, podem seleccionar tot en el mode edició i buscar **Face > triangulate face** se asegurar-nos de eliminar tots els ngons i després **Tris to quads**.  

Les superficies planes no necessiten polígons dins, es poden disoldre els "edges" sense problemes. Això serà més òptim per als motors i per al texturitzat. Una vegada creats els objectes, apliquem la rotació, localització i escala. Després entrem al mode edició i les optimitzem. Quan fem cilindres o esferes, es generen molts polígons que també es poden disoldre.

A banda de llevar polígons i evitar els ngons, les malles han de estar completes i les cares que estan en contacte han de formar part de la mateixa malla. Deguem unir amb **M** o manualment creant nous vertex totes les cares. No és precís que estiguen tancades per la part que no es veu. Amb **A, M** podem **unir per distància** i es completen les geometries que no estan unides, però estan tan juntes que no es nota.

La ferramenta de ganivet **K** és útil en aquest moment per crear més vores que trenquen en ngons o que permeten unir vertex propers de geometries que no estaven unides.

## Reparació de les "normals"

Un error molt greu és tindre cares que no estan ben orientades. Pel procés de modelat poden sorgir cares cap a fora que tenen la "normal" cap a dins. Cal rectificar totes les cares. Anem al menú de **View Overlays** i activem **Face Orientation** per veure les cares que no estan cap a fora. Ens els objectes tridimensionals, totes les cares visibles deurien tindre la "normal" cap a fora. Per solucionar el problema podem aplicar **Mesh > normals > Flip** a cada cara. Si la malla és complexa podem fer: **Mesh > normals > Recalculate Outside**.

En els objectes intencionalment bidimensionals, es pot indicar al motor de videojocs que mostre tant la cara de davant com la de darrere.

## Quantitat de polígons

Blender informa de les estadístiques emb una opció de visualització disponible dalt a la dreta. De vegades els encàrrecs o les necessitats del joc limiten els polígons que es poden utilitzar.

## Previsualització del resultat

> Amb el **Viewport Shading** es pot triar una imatge HDRi que ens ajude a veure cóm es veuen les geometries d'una manera més neta i aproximada al render. Podem configurar paràmetres fins trobar el que ens agrada o es sembla a l'ambient del joc. **Ambient Oclusion** pot servir per millorar la manera en que es comporten les llums i ombres. 

Moltes de les formes més subtils es poden aplicar després en el modelat en Alta i en el texturitzat.

En general deguem evitar els angles "negatius" que tanquen, ja que fan més difícil el texturitzat i el **bake**.

## En resum:

* Tots els polígons de 4 o 3 vores
* Cap ngon, cal triangular a mà.
* Llevar polígons, disolguent, de superfífices planes sense crear ngons. 
* Els vertex que estan molt prop es poden unir amb **M** i aplicant **K** quan necessitem vertex nous.
* Aplicar les transformacions als objectes.
* **Object > Set Origin > Origin to geometry**
* Completar malles, llevar les cares que no es veuran.
* Reparar les "normals".
* Revisar estadístiques.
* Confiar en la textura les imperfeccions subtils.
* Els objectes ja nets es poden anar guardant en una col·lecció. **M** En mode object. També podem posar-li nom i ocultar o evitar la selecció del que ja està. Posar nom als objectes és important per organització i per al **bake**. Una bona idea és afegir la paraula "_low" al nom per indicar que és la versió "low poly".
* Li podem afegir un material a cada objecte amb el mateix nom. També, encara que no fa falta, es pot canviar el color en el "viewport" a **Random** per diferenciar uns models d'altres. Aquest color no afecta al render.



