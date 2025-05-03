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

Los datos estan divididos en dos datasets, vino tinto y vino blanco.
_____
## **Vino Tinto**
Para este analisis estudiaremos principalmente el dataset de vino tinto

![Image](https://github.com/user-attachments/assets/3e34c043-e178-450d-a9b6-075082afb2ca)
![Image](https://github.com/user-attachments/assets/7c1f6695-fef0-492d-b039-bc89373d40a6)
![Image](https://github.com/user-attachments/assets/177f5d28-ee71-4785-a739-af78622f0086)

En el SO2 total tiene un par de valores anomalos. Estos valores se van a eliminar.

Ahora veamos cuales de estas propiedades se relacionan entre si:

![Image](https://github.com/user-attachments/assets/5357227b-f5f4-43ae-b57a-89f4ec2ec3bd)

* El pH está estrechamente relacionado con la acidez fija (de forma negativa), la acidez volátil (positiva) y el ácido cítrico (negativa), además de con otras variables entre sí. Esto tiene mucho sentido, ya que todas están asociadas a compuestos ácidos. También es lógico que estén correlacionadas porque pueden involucrar reactivos comunes.

* También es coherente que la densidad esté muy relacionada con el contenido de alcohol, ya que el alcohol tiene una densidad inferior a la del agua. Por otro lado, la mayoría de las demás sustancias disueltas tienden a incrementar la densidad.

* Es razonable que los vinos con mayor contenido de ácidos volátiles presenten menor concentración de alcohol. Esto podría deberse a que algunos ácidos volátiles se forman a partir del alcohol, o bien que una fermentación incompleta deje más compuestos intermedios.

* Parece que los consumidores valoran especialmente un mayor contenido de alcohol y una mayor concentración de ácido cítrico. Además, una concentración elevada de sulfatos también se asocia a una mejor calidad percibida.
Por el contrario, una mayor presencia de ácidos volátiles (posiblemente por sus aromas desagradables), SO2 (por su asociación con conservantes artificiales), y una baja densidad (que puede dar una sensación de “vino aguado” o excesivamente ligero) están negativamente correlacionadas con la calidad del vino


![Image](https://github.com/user-attachments/assets/7edcb241-01ff-4452-a275-b184efe6615a)

En esta grafica se ven estas correlaciones muy bien en esta grafica, ademas de mostrar las distribuciones de variables.

La acidez volatil, acido citrico, y alcohol tienen las distribuciones mas interesantes, vamos a estudiarlas mas de cerca.

#### Primero acidez volatil

![Image](https://github.com/user-attachments/assets/6095ff29-7dd0-4485-b562-82b0904c0273)

![Image](https://github.com/user-attachments/assets/1d9e09b9-a8e2-473d-a679-7b7bb1eba1a7)

Como se mencionó anteriormente, una menor concentración de ácido cítrico tiende a asociarse con una mayor calidad del vino. Sin embargo, las curvas mostraron que, independientemente de la calidad, las concentraciones suelen agruparse en torno a tres valores principales. Esta tendencia se observa de forma más clara y evidente en el histograma. Esto quiere decir que se podria estimar una concentracion optima.

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
#### **Todos los las variables**
Ahora veamos como se relacionan los tres a la vez.

![Image](https://github.com/user-attachments/assets/c040b7a1-4f4f-48b7-a29b-e8c68cabfd7a)


Hay demasiados vinos de baja calidad eclipsando la grafica.
Filtramos para solo ver los  vinos de maxima calidad:

![Image](https://github.com/user-attachments/assets/e75418f3-2478-4f60-b2d9-107f4e4423e5)

Los datos siguen siendo dispersos, pero las tendencias ahora son más claras y no se observan outliers. Parece que se pueden identificar dos grupos:

* Los vinos con una concentración media de ácido cítrico y acidez media.
* Los vinos con una baja concentración de ácido cítrico y una acidez volátil más alta.

Sin una simplificación de variables, es difícil determinar con certeza hasta qué punto estas tendencias son reales. Ahora, vamos a estudiar las distribuciones de los datos.

### **Estimación de la cocentración optima**

Para asegurarse de que los percentiles son fiables comprobamos si tienen una distribucion normal


|                      | statistic  | pvalue        |
|----------------------|------------|---------------|
| fixed acidity        | 8.350177   | 1.537383e-02  |
| volatile acidity     | 32.004587  | 1.122774e-07  |
| citric acid          | 7.388273   | 2.486892e-02  |
| residual sugar       | 103.852678 | 2.809813e-23  |
| chlorides            | 266.871920 | 1.120725e-58  |
| free sulfur dioxide  | 65.491076  | 6.008879e-15  |
| total sulfur dioxide | 56.227478  | 6.171040e-13  |
| density              | 3.824202   | 1.477696e-01  |
| pH                   | 8.940140   | 1.144651e-02  |
| sulphates            | 28.121259  | 7.826113e-07  |
| alcohol              | 1.984523   | 3.707373e-01  |
| quality              | 149.058290 | 4.289470e-33  | 

Considerando una significancia del 5% , ninguna variable tiene una distribución normal excepto alcohol, y la densidad. 
Aunque se puedan calcular los percentiles, al no tener una  una distribucion normal, la fiabilidad de estos queda en duda. 


|volatile acidity|citric acid|alcohol|sulphates|
|:----|:----|:----|:----|
|p_0|0.120|0.00|9.2|0.390|
|p_25|0.300|0.30|10.8|0.655|
|p_50|0.370|0.40|11.6|0.740|
|p_75|0.490|0.49|12.2|0.825|
|p_100|0.915|0.76|14.0|1.360|


Podríamos concluir que los vinos cuyas concentraciones de ácido cítrico, acidez volátil, sulfato y volumen de alcohol se sitúan en torno al percentil 50 tienden a presentar una calidad aceptable.

---
## **Conclusiones** 

Todos los acidos y el pH estan estrechamente relacionado entre si. Seguramente los acidos tengan rutas de síntesis relacionadas, y el pH mide la acidez.

La densidad esta relacionada con el volumen de alcohol. Esto es porque el alcohol tiene una densidad mas baja que el agua.

Tambien se ha relacionadp que los acidos volatiles estan negativamente relacionados con alcohol. Posiblemente los acidos volatiles se forman a partir de alcohol.

La calidad depende esta relacionada alcohol y la concentración de ácido cítrico en el vino. Además, una mayor concentración de sulfatos también se asocia con una mejor calidad percibida.
Por el contrario, los ácidos volátiles, el SO2 total y una baja densidad presentan una correlación negativa con la calidad.

Tambien se ha estudiado la concetracion optima de las 4 variables mas importantes:

* Ácido cítrico
* Acidez volátil
* Volumen de alcohol
* Sulfatos

Es importante señalar que este análisis solo ha considerado el efecto de tres variables (acidez volátil, ácido cítrico y volumen de alcohol) sobre la calidad del vino, sin estudiar las posibles relaciones o interacciones entre ellas. Realisticamente todas las variables y la relacion de estas afectarian a la calidad. En futuros analisis seria recomendable utilizar tecnicas de analisis multivariante como PCA.

Además, el conjunto de datos, además de ser relativamente antiguo, presenta varias limitaciones: solo contiene datos de una única variante de vino, incluye muy pocos vinos con una calidad superior a 8, dispone de pocas muestras con una calidad de 7 o más, y no contempla otros compuestos relevantes que influyen directamente en el sabor y aroma, como polifenoles, éteres o terpenos.

Estas conclusiones solo se aplicarian a esta variante del vino, ya que por ejemplo en el dataset del vino blanco (mas adelante) se han observo diferentes correlaciones (como por ejemplo una mayor importancia en de los cloruros y del SO2 libre y que el acido citrico no tenga impotancia directa).

![Image](https://github.com/user-attachments/assets/227b28ba-1a16-410a-9869-28e204f7204e)