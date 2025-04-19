# Efecto de las propiedades fisico químicas en vinos 

El dataset se saco de [de aqui](https://archive.ics.uci.edu/dataset/186/wine+quality).

Los datasets provienen de muestras de vino portugues "Vinho Verde". Para mas informacion consultar [la pagina web de Vinho Verde](http://www.vinhoverde.pt/), o el  [articulo de 2009 que ya lo ha estudiado](https://www.researchgate.net/publication/221612614_Using_Data_Mining_for_Wine_Quality_Assessment).

Cada dataset contiene siguientes fisico-quimicos faciles de analizar:

* ***Acidez fija***: Es la cantidad de ácidos del vino que no se evaporan. Estos pueden provenir tanto de la uva (como el ácido tartárico, málico o cítrico) como del proceso de fermentación (como el ácido succínico). La unidad en el dataset es g(ácido tartárico)/L.
* ***Acidez volatil***: Se refiere a la cantidad de ácidos que se pueden destilar del vino, principalmente ácido acético, aunque no es el único. A concentraciones de 1 g/L su olor se asemeja al vinagre. En el dataset se mide en g(ácido acético)/L. Existen procedimientos con dióxido de azufre para controlar esta variable
* ***Acido citrico***: Es un acidulante, también usado en la industria alimentaria. Se mide en g/L.
* ***Azucar residual***: Cantidad de azúcares que permanecen en el vino después de la fermentación. Se mide en g/L.
* ***Cloruros***: Cantidades de cloruro que provienen tanto de la uva como de otras sales añadidas para mejorar propiedades (por ejemplo el cloruro de plata ). Se mide en g(NaCl)/L. 
* ***Dioxido de Azufre total***:  Relacionado con los sulfitos, se emplea como conservante para evitar la oxidación de algunos compuestos. Su presencia debe ser advertida si supera los 10 mg/L. A partir de ahora se denominará SO2 total.
* ***Dioxido de Azufre libre***: Es la fracción del dióxido de azufre que no ha reaccionado con otros compuestos, por lo que permanece disponible para proteger al vino. Se mide en mg/L y en adelante se nombrará como SO₂ libre.  [<sup>1<sup>](https://extension.okstate.edu/fact-sheets/understanding-free-sulfur-dioxide-fso2-in-wine.html)
* ***Densidad***: Masa por unidad de volumen, medida en g/L.
* ***pH***: medida de acidez. Cuanto mas bajo, mas acido es el vino.
* ***Sulfatos***: Procedentes tanto de la planta como de la adición de sulfato de plata, que se utiliza para eliminar microorganismos no deseados. Se mide en g(K₂SO₄)/L.
* ***Alcohol***:  Porcentaje de volumen de etanol presente en el vino (% vol).

Y un valor de 1-10 de una cata a ciegas de la muestra.
[<sup>2<sup>](https://waterhouse.ucdavis.edu/whats-in-wine/fixed-acidity)

Primero estudiaremos el dataset del vino tinto.
| |fixed acidity|volatile acidity|citric acid|residual sugar|chlorides|free sulfur dioxide|total sulfur dioxide|density|pH|sulphates|alcohol|quality|
|:----|:----|:----|:----|:----|:----|:----|:----|:----|:----|:----|:----|:----|
|0|7.4|0.700|0.00|1.9|0.076|11.0|34.0|0.99780|3.51|0.56|9.4|5|
|1|7.8|0.880|0.00|2.6|0.098|25.0|67.0|0.99680|3.20|0.68|9.8|5|
|2|7.8|0.760|0.04|2.3|0.092|15.0|54.0|0.99700|3.26|0.65|9.8|5|
|3|11.2|0.280|0.56|1.9|0.075|17.0|60.0|0.99800|3.16|0.58|9.8|6|
|4|7.4|0.700|0.00|1.9|0.076|11.0|34.0|0.99780|3.51|0.56|9.4|5|
|...|...|...|...|...|...|...|...|...|...|...|...|...|
|1594|6.2|0.600|0.08|2.0|0.090|32.0|44.0|0.99490|3.45|0.58|10.5|5|
|1595|5.9|0.550|0.10|2.2|0.062|39.0|51.0|0.99512|3.52|0.76|11.2|6|
|1596|6.3|0.510|0.13|2.3|0.076|29.0|40.0|0.99574|3.42|0.75|11.0|6|
|1597|5.9|0.645|0.12|2.0|0.075|32.0|44.0|0.99547|3.57|0.71|10.2|5|
|1598|6.0|0.310|0.47|3.6|0.067|18.0|42.0|0.99549|3.39|0.66|11.0|6|


![Image](https://github.com/user-attachments/assets/3e34c043-e178-450d-a9b6-075082afb2ca)
![Image](https://github.com/user-attachments/assets/7c1f6695-fef0-492d-b039-bc89373d40a6)
![Image](https://github.com/user-attachments/assets/177f5d28-ee71-4785-a739-af78622f0086)


Ahora veamos cuales de estas propiedades se relacionan entre si:

![Image](https://github.com/user-attachments/assets/5357227b-f5f4-43ae-b57a-89f4ec2ec3bd)

La acidez volatil, acido citrico, y alcohol tienen las distribuciones mas interesantes, vamos a estudiarlas mas de cerca.

Nos centraremos en la calidad:
* Negativamente Acidez volatil (-0.39)
* Acido citrico(0.23)
* Negativamente con al SO2 total(-0.19)
* Negativamente con la densidad(-0.17)
* Sulfatos (0.25)
* Alcohol(0.48)
    
Parece que los expertos valoran especialmente el contenido de alcohol y la concentración de ácido cítrico en el vino. Además, una mayor concentración de sulfatos también se asocia con una mejor calidad percibida.
Por el contrario, los ácidos volátiles, el dióxido de azufre (SO₂) y una baja densidad presentan una correlación negativa con la calidad.


![Image](https://github.com/user-attachments/assets/7edcb241-01ff-4452-a275-b184efe6615a)

La acidez volatil, acido citrico, y alcohol tienen las distribuciones mas interesantes, vamos a estudiarlas mas de cerca.


#### Primero acidez volatil

![Image](https://github.com/user-attachments/assets/6095ff29-7dd0-4485-b562-82b0904c0273)

![Image](https://github.com/user-attachments/assets/1d9e09b9-a8e2-473d-a679-7b7bb1eba1a7)

Como se mencionó anteriormente, una menor concentración de ácido cítrico tiende a asociarse con una mayor calidad del vino. Sin embargo, las curvas mostraron que, independientemente de la calidad, las concentraciones suelen agruparse en torno a tres valores principales. Esta tendencia se observa de forma más clara y evidente en el histograma.

#### Ahora acido citrico
![Image](https://github.com/user-attachments/assets/30b21381-4005-4f27-80fc-06d82430ac49)

![Image](https://github.com/user-attachments/assets/8b00a7ff-eb40-40ea-ae2e-2aa2ccb45438)

Aquí ocurre algo similar. En las curvas se observan tres niveles definidos, sin embargo, en el histograma esta tendencia no resulta tan evidente, lo que sugiere que la muestra podría ser demasiado pequeña para confirmar este patrón con certeza. Estos “tres niveles” parecen corresponder aproximadamente a las concentraciones de 0,00; 0,25 y alrededor de 0,50.

#### Ahora contenido en alcohol

![Image](https://github.com/user-attachments/assets/d0ef95a3-2e2c-4576-be55-e71635f0899e)

![Image](https://github.com/user-attachments/assets/9fb962fd-a243-4340-b08a-649467400e3c)

Se puede observar que los vinos de menor calidad presentan una concentración de alcohol más baja, aproximadamente en torno al 9,5%. En cambio, los vinos de mayor calidad muestran una distribución mucho más dispersa, aunque tienden a concentrarse mayoritariamente en valores más altos de alcohol.


#### Finalmente sulfatos
![Image](https://github.com/user-attachments/assets/9738cde8-525d-4d39-8b89-e60aec0270f3)

Parece que los vinos de calidad inferior presentan una mayor variabilidad en la concentración de sulfatos, lo que podría indicar un menor control durante su elaboración. Por el contrario, los vinos de mayor calidad no solo muestran concentraciones menos dispersas, sino que además tienden a agruparse en torno a los 0,75 g/L.


-------
Ahora veamos como se relacionan los tres a la vez.

![Image](https://github.com/user-attachments/assets/c040b7a1-4f4f-48b7-a29b-e8c68cabfd7a)


Hay demasiados vinos de baja calidad eclipsando la grafica.
Filtramos para solo ver los  vinos de maxima calidad:

![Image](https://github.com/user-attachments/assets/f2d4b960-797c-4741-9664-28f3abc2ee92)

Aunque que se vean de forma clara son datos demasiado dispersos y escasos como para ver una tendencia clara.
![Image](https://github.com/user-attachments/assets/e75418f3-2478-4f60-b2d9-107f4e4423e5)

Los datos siguen siendo dispersos, pero las tendencias ahora son más claras y no se observan outliers. Parece que se pueden identificar dos grupos:

* Los vinos con una concentración media de ácido cítrico y acidez media.
* Los vinos con una baja concentración de ácido cítrico y una acidez volátil más alta.

Sin una simplificación de variables, es difícil determinar con certeza hasta qué punto estas tendencias son reales. Ahora, vamos a estudiar las distribuciones de los datos.

(Agruparemos las variables de ácido cítrico y acidez volátil para ahorrar espacio).


![Image](https://github.com/user-attachments/assets/2333e0f1-9048-4ced-a622-5bcc869c4aef)


![Image](https://github.com/user-attachments/assets/3afd6f83-730e-4ff7-b9f3-845b76591cf6)

![Image](https://github.com/user-attachments/assets/b511e569-30e9-48e1-b6fd-9fe3f9f9a076)

Recordemos que los percentiles del ácido cítrico no serán del todo representativos, ya que la variable no sigue una distribución normal.
Aun así, se observa que existen vinos con una concentración muy baja y otros con una concentración media, lo que sugiere la presencia de dos grupos bien diferenciados.

|volatile acidity|citric acid|alcohol|
|:----|:----|:----|
|p_0|0.120|0.00|9.2|
|p_25|0.300|0.30|10.8|
|p_50|0.370|0.40|11.6|
|p_75|0.490|0.49|12.2|
|p_100|0.915|0.76|14.0|

Podríamos concluir que los vinos cuyas concentraciones de ácido cítrico, acidez volátil y volumen de alcohol se sitúan en torno al percentil 50 tienden a presentar una calidad aceptable.

Sin embargo, es importante señalar que este análisis solo ha considerado el efecto de tres variables (acidez volátil, ácido cítrico y volumen de alcohol) sobre la calidad del vino, sin estudiar las posibles relaciones o interacciones entre ellas. En futuros analisis seria recomendable utilizar tecnicas de analisis multivariante como PCA.

Además, el conjunto de datos, además de ser relativamente antiguo, presenta varias limitaciones: solo contiene datos de una única variante de vino, incluye muy pocos vinos con una calidad superior a 8, dispone de pocas muestras con una calidad de 7 o más, y no contempla otros compuestos relevantes que influyen directamente en el sabor y aroma, como polifenoles, éteres o terpenos.

Finalmente aunque el efecto del sulfato en la calidad es conocido no se ha estudiado suficiente.

----
Otra duda que surge es:¿Son estos factores distintos en el vino blanco?




