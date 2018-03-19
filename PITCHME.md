## UML
- Conjunt de diagrames  modelitzar l'etapa de disseny.
- Què obtenim?
	- Especificar de manera gràfica els 
	- Posar el breakpoint a la línia que hi ha l'error
	- Mostrar les variables implcades com evoluionen i trobar l'error
---
## Classe
 	- És l'especificació d'objectes amb característiques i comportaments similars.
 	- Al programar aquesta classe, després podrem usar objectes d'aquesta.
---
Exemples:  
	* [Formulari inscripció] (https://alacarral.net/images/documents/estiu2017/inscripcio_estiu_2017.pdf)
	* [IKEA](https://www.ikea.com/es/es/assembly_instructions/alex-cajonera__AA-844481-2_pub.pdf)
	* [Coche lego] (https://www.lego.com/biassets/bi/4639848.pdf)
---
## Propietats / atributs
	- Quines dades fan especial a cada objecte (element) de la classe.
	- Les propietats són valors que es necessiten.
	- Cada propietat té un tipus i un valor.
	- *Es defineixen com a variables de la classe*
--- 
## Mètodes
	- Són les accions que pot fer cada objecte de la classe.
	- Es defineixen 
--- 
## Visiblitat dels mètodes / atributs
	- privats Només es visible en l'àmbit de programaci de la classe. UML és - 		
	- públics visible per tothom. UML és +
	- protegits visible per les classes que heredin. UML és #
	- package només a nivell del paquiet on estan definides les classes. UML és ~
---
## Atributs / mètodes inherents 

Quan programem una classe tenim un objecte que ens ve definit. És el objecte en si mateix de la classe. 
El que s'està creant. En Java és **this** i en Python és **self**

També hi ha una sèrie de mètodes que estan ja predefinits al fer una classe. Per exemple: com convertir un objecte a String.
---
## Traducció a UML
Usarem eines gràfiques:
	- [Extensió per a Eclipse] (https://marketplace.eclipse.org/content/uml-designer)
	- Lucid Chart (incorporat al Drive)
	- [Draw.io](http://www.draw.io)
O qui vulgui codificant usant [PlantUML](http://plantuml.com/class-diagram)
--- 
## Exemple UML
Classe persona:
```planUML
@startuml
class Persona {
  +String nom
  -int edat 
  #String dni
  
  -int setEdat()
  +int getEdat()
  ~String getDni()	
}
@enduml
```
---
## Diagrama 
Usant [Gravizo](http://ww.gravizo.com) , es posa la URL de la imatge https://g.gravizo.com/svg? seguit de la descripció.
Des de (http://ww.gravizo.com/#converter)
![UML](<img src='https://g.gravizo.com/svg?
@startuml;

class Persona {;
  +String nom;
  -int edat ;
  %23String dni;
  ;
  -int setEdat%28%29;
  +int getEdat%28%29;
  ~String getDni%28%29	;
};)
---
## Obecte / Instanciació
### Constructors
Mètodes que es criden quan es crea un objecte d'una classe.
```java
public class Persona {
	String nom;
	private int edat;
	public Persona(String nom, int edat){
		this.nom=nom;
		this.edat=edat;
	}
	public boolean esMajor(){
		if(this.edat>=18) return true;
		return false;
	}
}
```
---
```python
class Persona: 
	nom=''
	__edat=0
	def __init__(self, nom,edat):
		self.nom=nom
		self.edat=edat
	def esMajor(self):
		if (self.edat >= 18):
			return true
		return false			
```
---
# Instanciació de l'objecte
Quan un objecte es crea, prèn valors, significa que **aquella variable** és instància de la classe.
Com es creen?
```java
public class Institut {
	public static void main(String args[]){
		Persona p = new Persona("Sergi Pérez",23);
	}
}
```
```python
p = Persona("Sergi Pérez",23)
```
--- 
Com treballem amb els objectes, posant un . després de la variable i aleshores escrivint el nom de la propietat o cridant al mètode.
```java
public class Institut {
	public static void main(String args[]){
		Persona p = new Persona("Sergi Pérez",23);
		if (p.esMajor()) System.out.println(p.nom);
	}
}
```
```python
p = Persona("Sergi Pérez",23)
if (p.esMajor()) print(p.nom)
```
--- 
# Relacions entre classes: herència, composició i agregació
---
# Sobrecàrrega
---
# Encapsulament / seguretat
---
# Polimorfisme
--- 
