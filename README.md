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

Se ha estudiado el eefecto de estas variables en la calidad en el [vino tinto](## Vino Tinto) y en [vino blanco](## Vino Blanco)
_____
## Vino Tinto

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

Nos centraremos en la calidad con cut-off de 0.15:
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
## Vino Blanco
Otra duda que surge es:¿Son estos factores distintos en el vino blanco?

|fixed acidity|volatile acidity|citric acid|residual sugar|chlorides|free sulfur dioxide|total sulfur dioxide|density|pH|sulphates|alcohol|quality|
|:----|:----|:----|:----|:----|:----|:----|:----|:----|:----|:----|:----|
|0|7.0|0.27|0.36|20.7|0.045|45.0|170.0|1.00100|3.00|0.45|8.8|6|
|1|6.3|0.30|0.34|1.6|0.049|14.0|132.0|0.99400|3.30|0.49|9.5|6|
|2|8.1|0.28|0.40|6.9|0.050|30.0|97.0|0.99510|3.26|0.44|10.1|6|
|3|7.2|0.23|0.32|8.5|0.058|47.0|186.0|0.99560|3.19|0.40|9.9|6|
|4|7.2|0.23|0.32|8.5|0.058|47.0|186.0|0.99560|3.19|0.40|9.9|6|
|...|...|...|...|...|...|...|...|...|...|...|...|...|
|4893|6.2|0.21|0.29|1.6|0.039|24.0|92.0|0.99114|3.27|0.50|11.2|6|
|4894|6.6|0.32|0.36|8.0|0.047|57.0|168.0|0.99490|3.15|0.46|9.6|5|
|4895|6.5|0.24|0.19|1.2|0.041|30.0|111.0|0.99254|2.99|0.46|9.4|6|
|4896|5.5|0.29|0.30|1.1|0.022|20.0|110.0|0.98869|3.34|0.38|12.8|7|
|4897|6.0|0.21|0.38|0.8|0.020|22.0|98.0|0.98941|3.26|0.32|11.8|6|


![Image](https://github.com/user-attachments/assets/4c9f4581-54fe-421e-948a-a7f5c902c9b9)

Curiosamente en el vino blanco los parametros relacionados con la calidad son distintos.
* Acidez volatil (-0.19)
* Cloruros (-0.21)
* SO2 total (-0.17)
* Densidad (-0.31)
* Alcohol (0.44)
* 
Curiosamente, los parámetros no coinciden con los del vino tinto. En ambos casos, parece valorarse positivamente un mayor contenido de alcohol y negativamente una alta acidez volátil, una densidad elevada y un alto contenido de SO₂ total.
Sin embargo, en el vino blanco, el ácido cítrico y los sulfatos parecen tener un efecto menos significativo, mientras que los cloruros influyen en mayor medida.

![Image](https://github.com/user-attachments/assets/85175319-c11d-4309-be26-74608af3a7be)

En comparacion con el dataset del vino tinto, este dataset contiene outliers mas visibles, vamos a eliminarlos. 
Se eliminaron los puntos 2781, 1526, 47451653, 1663, y 745.

---
Tras quiltar los valores anomalos no parece que haya muchos cambios.

![Image](https://github.com/user-attachments/assets/227b28ba-1a16-410a-9869-28e204f7204e)


Veamos los histogramas de todos los valores
![Image](https://github.com/user-attachments/assets/56de317f-77c7-40b4-a5dc-d79182e6aba0)
![Image](https://github.com/user-attachments/assets/0cd8e49c-0a4a-4871-b6fd-261164cac058)
![Image](https://github.com/user-attachments/assets/7643e66d-5b74-4531-8faa-18b3ad697934)

Parece que siguen una distrbucion normal, aunque es dificl ver los detalles.

![Image](https://github.com/user-attachments/assets/1ec7e841-7007-4b1a-938d-0b7e09d162a7)

En este conjunto de datos se observan de forma muy clara algunas correlaciones, como la del pH con la acidez fija o la de la densidad con el azúcar residual 
Las distribuciones de azúcar residual, ácido cítrico, alcohol, densidad y sulfatos resultan especialmente interesantes, por lo que vamos a analizarlas con mayor detalle.

#### Azúcar residual
![Image](https://github.com/user-attachments/assets/1dfac6bc-83c3-46a2-8f70-9506b52da3f7)

![Image](https://github.com/user-attachments/assets/414abc73-7c32-41d0-a8f5-090ce96f15fb)


#### Ácido cítrico

![Image](https://github.com/user-attachments/assets/411475e2-8f0d-45b0-84e1-980658442172)

![Image](https://github.com/user-attachments/assets/f4fcb4ed-0f42-46dd-87c9-905be0639d73)


#### Alcohol

![Image](https://github.com/user-attachments/assets/58907b38-b604-4f99-8855-fb516dfaf7d3)

![Image](https://github.com/user-attachments/assets/e2869177-d6c8-4d29-81b6-35f67e6aa7a3)


#### Densidad

![Image](https://github.com/user-attachments/assets/255193f1-a8af-4640-adcf-08d14d9a8326)
![Image](https://github.com/user-attachments/assets/7f73667e-5952-430d-b15b-083f10e12d67)


---


![Image](https://github.com/user-attachments/assets/061ba52c-e227-487b-90bd-b800bb7a987f)

Hay demasiados datos muy dispersos. Vamos a filtrarlos a partir del 7.


![Image](https://github.com/user-attachments/assets/71b87556-89a9-4939-9fca-a890c61ebe4a)

Parece que la mayoria esta en la zona central. Podemos estimar una zona donde la calidad sea alta.



|volatile acidity|	citric acid|	alcohol|	sulphates|	chlorides|
-----------------|-------------|-----------|-------------|-----------|
p_0|	0.08|	0.01|	8.5|	0.22|	0.012|
p_25|	0.19|	0.28|	10.7|	0.40|	0.031|
p_50|	0.25|	0.31|	11.5|	0.48|	0.037|
p_75|	0.32|	0.36|	12.4|	0.58|	0.044|
p_100|	0.76|	0.74|	14.2|	1.08|	0.135|


El ácido cítrico y el alcohol presentan concentraciones bastante similares, mientras que los sulfatos y la acidez volátil muestran valores más bajos en comparación.

La mayoría de estas variables exhiben distribuciones que se aproximan a una distribución normal, lo que permite estimar sus percentiles con mayor fiabilidad en comparación con el dataset anterior.

No obstante, los histogramas revelan que este conjunto de datos contiene un mayor número de muestras que se sitúan fuera de los límites habituales.

Al igual que en el dataset anterior, se observa que hay pocas muestras correspondientes a vinos de alta calidad. Cabe destacar que este análisis sigue siendo univariante, es decir, no considera las relaciones o interacciones entre variables, un aspecto que debería abordarse en futuros análisis.

A pesar de ello, este conjunto de datos cuenta con un número de muestras significativamente mayor, lo que podría permitir obtener resultados más robustos.

