## Modelar una partida d'escacs

Us han contractat per desenvolupar (preferiblement en Java) un joc que permeti a dues persones jugar a escacs.

Una partida consta de dos jugadors i un tauler. 

El tauler té 8 files i 8 columnes, inicialment 32 peces i indica sempre a quin jugador li toca jugar cada cop.
Quan el tauler es crea les 32 peces es posen en la seva [posició inicial](https://ca.wikipedia.org/wiki/Reglament_dels_escacs#Posici%C3%B3_inicial) i indica que li toca jugar al jugador que té el color blanc. 

El tauler sap pintar-se per pantalla de la següent manera: 

|  | 1| 2| 3| 4| 5| 6| 7| 8|
|--|--|--|--|--|--|--|--|-- |
|8|TN|CN|AN|DN|RN|AN|CN|TN|
|7|PN|PN|PN|PN|PN|PN|PN|PN|
|6|  |  |  |  |  |  |  |  |
|5|  |  |  |  |  |  |  |  |
|4|  |  |  |  |  |  |  |  |
|3|  |  |  |  |  |  |  |  |
|2|PB|PB|PB|PB|PB|PB|PB|PB|
|1|TB|CB|AB|DB|RB|AB|CB|TB|
 

Col·locant sempre les peces de color blanc a la fila 1, la més inferior.
El tauler demana a una peça [quins moviments](https://ca.wikipedia.org/wiki/Reglament_dels_escacs#Moviment_de_les_peces) pot fer (a quines caselles pot anar) i després filtra aquests moviments pels possibles (tauler sap on estan les altres fitxes i anul·la aquelles caselles que estan obstaculitzades per altres peces).

El tauler sap detectar quan una partida s'ha acabat i indica quin jugador és el guanyador.

Les peces poden ser de color blanc o negra i saben que estan situades en una fila i columna concretes del tauler. A més saben canviar la seva posició, donada una altra posició del tauler es situen. També saben dir quins moviments poden realitzar, quins moviments poden ser possibles, des d'on estan.

Hi ha diversos tipus de peces, tenim:
- El peó: 
  - Quan es pinta per pantalla mostra una P i segons el seu color serà PB (peó blanc) o PN (peó negre).
  - Els possibles moviments d'un peó:
     - Són augmentar (cas blanques)  o disminuir (cas negres) la seva fila en una. 
     - Si està en la casella inicial pot moure's també a dues files superiors (banques) o inferiors (negres).
     - I matar:
        - Per les blanques: augmentar columna i fila en una, disminuir columna en una i augmentar fila en una.
        - Per les negres: disminuir columna i fila en una, augmentar columna en una i disminuir fila en una.
- La torre:
  - Quan es pinta per pantalla mostra una T i segons el seu color serà TB o TN.
  - Els possibles moviments d'una torre:
     - Totes les caselles de la fila en la que està excepte la seva.
     - Totes les caselles de la columna en la que està excepte la seva.
- L'alfil:
  - Quan es pinta per pantalla mostra una A i segons el seu color serà AB o AN.
  - Els possibles moviments d'un alfil:
     - Pot moure's en tots els sentits de la diagonal que ocupa.
- La dama (*reina*):
  - Quan es pinta per pantalla mostra una D i segons el seu color serà DB o DN .
  - Els possibles moviments de la dama són la suma dels moviments de la torre més els del alfil.   
- El rei:
  - Quan es pinta per pantalla mostra una R i segons el seu color serà RB o RN.
  - Els possibles moviments d'un rei són totes les seves caselles veïnes. (A distància d'una fila o columna). Per tant 8 caselles.
- El cavall:
  - Quan es pinta per pantalla mostra una C i segons el seu color serà CB o CN.
  - Els possibles moviments d'un cavall són 8 caselles i s'obtenen: mou en forma de 'L' -> avança dues caselles en qualsevol dels quatre sentits ortogonals (seguint una fila o una columna), i una casella perpendicularment a les anteriors. 

Els jugadors s'identifiquen per un correu electrònic i saben quin color tenen. Al crear-se se'ls assigna un color i donen el seu correu electrònic.

El jugador un cop se li mostra el tauler, indica al tauler quina peça vol moure: tria fila i columna. Aleshores el tauler li comunica al jugador a quines posicions pot moure la peça seleccionada i el jugador tria el moviment.
Un cop triat al moviment aquella peça s'haurà de moure.


### Valoració (mireu rúbrica la Moodle)

Es valora:
- Detecció de les classes correctament ( 1 punts )
- Detecció i definició de les propietats de cada classe ( 1 punts )
- Detecció i definició dels mètodes de cada classe ( 1 punts )
- Detecció adequada de la visibilitat de cada propietat i mètode ( 0.5 punts )
- Detecció de propietats o mètodes estàtics ( 0.5 punts )
- Detecció de propietats / mètodes / classes abstractes ( 0.5 punts )
- Definició dels diversos constructors ( 0.5 punts )
- El disseny permet una implementació totalment encapsulada ( 1 punts )
- Sobreescriptura de mètodes genèrics de Java ( 0. 5 pùnts )
- Detectada les relacions entre les classes:
   - Herència ( 1 punts )
   - Agregació ( 1 punts )
   - Associació ( 1 punts )
- El disseny permet aplicar polimorfisme ( 0.5 punts )


