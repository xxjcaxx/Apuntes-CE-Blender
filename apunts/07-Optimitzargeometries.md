# Optimitzar Geometries

Els motors de jocs van a triangular totes les geometries. Les cares de 3 i 4 vores són perfectes per triangular, però els ngons no. Les cares de 3 vores no permeten els loops i dificulten el modelat. Per tant, utilitzarem cares de 4 o quads sempre que es puga i les de 3 per triangular i completar malles.

Normalment la triangulació de ngons s'ha de fer manualment abans de passar al motor de jocs.

Les superficies planes no necessiten polígons dins, es poden disoldre els "edges" sense problemes. Això serà més òptim per als motors i per al texturitzat. Una vegada creats els objectes, apliquem la rotació, localització i escala. Després entrem al mode edició i les optimitzem.

A banda de llevar polígons i evitar els ngons, les malles han de estar completes i les cares que estan en contacte han de formar part de la mateixa malla. Deguem unir amb **M** o manualment creant nous vertex totes les cares. No és precís que estiguen tancades per la part que no es veu.

Un error molt greu és tindre cares que no estan ben orientades. Pel procés de modelat poden sorgir cares cap a fora que tenen la "normal" cap a dins. Cal rectificar totes les cares. 

Blender informa de les estadístiques emb una opció de visualització disponible dalt a la dreta. De vegades els encàrrecs o les necessitats del joc limiten els polígons que es poden utilitzar. 

Moltes de les formes més subtils es poden aplicar després en el modelat en Alta i en el texturitzat. 

En resum:

* Tots els polígons de 4 o 3 vores
* Cap ngon, cal triangular a mà.
* Llevar polígons, disolguent, de superfífices planes sense crear ngons. 
* Els vertex que estan molt prop es poden unir amb **M**.
* Aplicar les transformacions als objectes.
* Completar malles, llevar les cares que no es veuran.
* Reparar les "normals".
* Revisar estadístiques.
* Confiar en la textura les imperfeccions subtils. 
