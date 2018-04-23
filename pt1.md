## Modelar una partida d'escacs

Us han contractat per desenvolupar (preferiblement en Java) un joc que permeti a dues persones jugar a escacs.

Una partida consta de dos jugadors i un tauler. 
El tauler té 8 files i 8 columnes, inicialment 16 peces i indica a quin jugador li toca jugr cada cop.
Quan el tauler es crea les 16 peces es posen en la seva [posició inicial](https://ca.wikipedia.org/wiki/Reglament_dels_escacs#Posici%C3%B3_inicial) i indica que li toca jugar al jug

Les peces poden ser de color blanc o negra i saben que estan situades en una fila i columna concretes del tauler. A més saben canviar la seva posició, donada una altra posició del tauler es situen. També saben dir quins moviments poden realitzar, quins moviments poden ser possibles, des d'on estan.
Les peces també saben com mostrar-se per pantalla, com escriure's.

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
  - Quan es pinta per pantalla mostra una T i segons el seu color serà TB (peó blanc) o TN (peó negre).
  - Els possibles moviments d'una torre:
     - Totes les caselles de la fila en la que està excepte la seva.
     - Totes les caselles de la columna en la que està excepte la seva.
- L'alfil:
  - Quan es pinta per pantalla mostra una A i segons el seu color serà AB (peó blanc) o AN (peó negre).
  - Els possibles moviments d'un alfil:
     - Pot moure's en diagonal. Per tant fins a 8 (límit de la darrera fila i columna del tauler) fa: 
- La dama (*reina*):
  - Quan es pinta per pantalla mostra una D i segons el seu color serà DB (peó blanc) o DN (peó negre).
  - Els possibles moviments de la dama són la suma dels moviments de la torre més els del alfil.   
- El rei:
  - Quan es pinta per pantalla mostra una R i segons el seu color serà RB (peó blanc) o RN (peó negre).
  - Els possibles moviments d'un rei són totes les seves caselles veïnes. (A distància d'una fila o columna). Per tant 8 caselles.
-  

Els jugadors s'identifiquen per un correu electrònic i saben quin color tenen. Al crear-se se'ls assigna un color i donen el seu correu electrònic.
El jugador un cop se li mostra el tauler, pot triar una peça del tauler: tot indicant la fila i la columna. Aleshores el tauler li comunica al jugador a quines posicions pot moure la fitxa i el jugador tria el moviment.
Un cop triat al moviment aquella peça s'haurà de moure.
