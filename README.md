# ** Efecto de las propiedades fisico químicas en vinos **

El dataset se saco de [de aqui](https://archive.ics.uci.edu/dataset/186/wine+quality).

Los datasets provienen de muestras de vino portugues "Vinho Verde". Para mas informacion consultar [la pagina web de Vinho Verde](http://www.vinhoverde.pt/), o el  [articulo de 2009 que ya lo ha estudiado](https://www.researchgate.net/publication/221612614_Using_Data_Mining_for_Wine_Quality_Assessment).

Cada dataset contiene siguientes fisico-quimicos faciles de analizar:

* ***Acidez fija***: Es la cantidad de acidos del vino que no se evaporan.Pueden provenir tanto de la uva (como los acidos tartarico, malico o citrico) como de la fermentacion (como el acido succinico). La unidad de dataset es (g(acido tartarico)/L).
* ***Acidez volatil***: Se refiere a la cantidad de acidos destilables en el vino, sobre todo el acido acetico, aunque no sea el unico. a 1 g/L tiene un olor que se asemeja al vinagre. El dataset lo mide eng(acido acetico)/L. 
Existen procedimientos  con dioxido de azufre para controlar esta variable.
* ***Acido citrico***: un acidulante usado en la inductria. (g/l)
* ***Azucar residual***: es la cantidad de azucares que queda  tras la fermentacion g/l
* ***Cloruros***: cantidades de cloruro probenientes de de la uva junto con otras sales que son añadidas para mejorar propiedades( como AgCl) (g(NaCl)/L). 
* ***Dioxido de Azufre total***: Estan relacionado con los sulfitos. Se usa como conservante para inhibir la oxidacion de algunos compuestos. Deben avisar si supera los 10 mg/l, erpo nor. A partir de ahora se referira a este compuesto como SO2.
* ***Dioxido de Azufre libre***: SO2 que  que no reaccionan a  sulfitos con el tiempo (mg/L). A partir de ahora SO2 libre. [<sup>1<sup>](https://extension.okstate.edu/fact-sheets/understanding-free-sulfur-dioxide-fso2-in-wine.html)

* ***Densidad***: g/L.
* ***pH***: medida de acidez. Cuanto mas bajo, mas acido es el vino.
* ***Sulfatos***: provenientes de la planta  o de echar sulfato de plata paraa eliminar microorganismos g(K2SO4/L).
* ***Alcohol***:  en vol%
  
Y un valor de 1-10 de una cata a ciegas de la muestra.
[<sup>2<sup>](https://waterhouse.ucdavis.edu/whats-in-wine/fixed-acidity)

