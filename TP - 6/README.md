link: https://github.com/AJVelezRueda/Bioinfo_UNQ/blob/master/Trabajos_Practicos/Inferencias_evolutivas/Tp_inferencias_evolutivas.pdf


>bartmosca 
MGSGDAENGKKIFVQKCAQCHTYEVGGKHKTGPNLHGLFGRKTGQAPGYSYTAANKNKGIIWGEDTLMEYLENPKKYIPGTKMIFVGIKKKEERADLIAYLKKATNE

>NP_061820.1 cytochrome c [Homo sapiens]
MGDVEKGKKIFIMKCSQCHTVEKGGKHKTGPNLHGLFGRKTGQAPGYSYTAANKNKGIIWGEDTLMEYLENPKKYIPGTKMIFVGIKKKEERADLIAYLKKATNE

>AEP27192.1 cytochrome c [Gorilla gorilla] MGDVEKGKKIFIMKCSQCHTVEKGGKHKTGPNLHGLFGRKTGQAPGYSYTAANKNKGIIWGEDTLMEYLENPKKYIPGTKMIFVGIKKKEERADLIAYLKKATNE

>NP_477164.1 cytochrome c distal isoform A [Drosophila melanogaster]  MGSGDAENGKKIFVQKCAQCHTYEVGGKHKVGPNLGGVVGRKCGTAAGYKYTDANIKKGVTWTEGNLDEYLKDPKKYIPGTKMVFAGLKKAEERADLIAFLKSNK

>NP_001065289.1 cytochrome c [Pan troglodytes] MGDVEKGKKIFIMKCSQCHTVEKGGKHKTGPNLHGLFGRKTGQAPGYSYTAANKNKGIIWGEDTLMEYLENPKKYIPGTKMIFVGIKKKEERADLIAYLKKATNE


**Reto I: Detalla las tácticas y/o metodologías que deberían utilizarse para darles una respuesta a los padres del niño.** 
***Dadas las secuencias de Mosca, humano y Moscahumano ¿Qué criterios se les ocurren para comparar las secuencias? ¿Qué resultados obtienen del análisis anterior?***
-- En una versión pormenorizada, realizariamos el análisis realizando la alineación y comparación entre las tres secuencias mencionadas. El resultado, derivaría en un árbol filogenético, el cual se encuentra resumido al confeccionarse considerando tan solo esas secuencias anteriormente mencionadas. Se dice que es pormenorizado, dado el bajo número de muestras participantes que se analizan para el mismo.


***¿Qué resultado esperaría obtener si utilizara el resto de las secuencias en el análisis? ¿Por qué?***

-- Para poder comparar a las secuencias de los tres organismos mencionados no basta con alinear y realizar la comparación entre las mismas, ya que esto no sería del todo preciso ni estaría mostrando el  panorama real. Para poder obtener algo más parecida a la realidad, debemos comparar esta secuencia con varias secencias de varias especies, por ejemplo, las secuencias de los mamíferos, donde estará la del humano, y con las de los insectos, donde estará la de la mosca, pero tambien existiran otras muchas especies. Esto visión, mucho más transversal, nos dará un árbol más grande  donde veremos una distancia más correcta entre las secuencias de estas tres “especies” a dadas. Mayor cantidad de datos, puede permitir una respuesta mucho mas precisa.



**Reto II: Como vimos anteriormente existen algunos softwares optimizados para confeccionar alineamientos de secuencias. En particular hemos trabajado con Clustal (Larkin et al. 2007). Confecciona los alineamientos para los del punto I.a y I.b análisis.**

**I.a :**
![A](https://github.com/pache0015/Bioinformatica-UNQ/blob/master/TP%20-%206/img/a.jpg)

**I.b :**
![B](https://github.com/pache0015/Bioinformatica-UNQ/blob/master/TP%20-%206/img/b.png)

-- Si bien en este árbol filogenético no se analizan una gran cantidad de secuencias, se hizo a modo de ejemplificar la respuesta dada en el punto I.a. 

**Reto III: Mediante el uso del servidor de IQtree (Trifinopoulos et al. 2016), confecciona los árboles filogenéticos para los alineamientos obtenidos en el punto II.**
***Como vemos, el servidor nos permite elegir el modelo de sustitución ¿A qué se refiere?***
***¿Qué es el Bootstrap? ¿De qué manera nos habla de la calidad de nuestro árbol? ¿Cómo influye el número de Bootstraps en el resultado?***
***Interpreten los resultados obtenidos, mediante la visualización de los árboles con la herramienta FigTree. ¿Es necesario realizar algún paso extra, previo a la interpretación del árbol? ¿Por qué?***


Para responder a que se refiere que el servidor permita elegir el modelo de sustitución, deberiamos inicialmente definirlo. En la biología evolutiva existe una estructura llamada matriz de sustitución, la cual describe el ritmo al que un carácter en una secuencia muta a otro carácter a traves del paso del tiemputilizadas usualmente en el proceso de alineamiento de secuencias de aminoácidos o ADN, donde la similitud entre secuencias depende del tiempo desde su divergencia y de los ritmos de sustitución según se representan en la matriz. Estas matrices se asoacian como parámetros de los algoritmos de alineamiento (por ejemplo los de Needlemann-Wunsch o Smith-Waterman,, ya mencioados y vistos durante la cursada). Estos cumplen el papel de asignar una determinada puntuación a cada emparejamiento entre los aminoácidos de las secuencias a alinear, contribuyendo así a la puntuación global del alineamiento. 
Las matrices de sustitución se diferencian, principalmente, en los fundamentos para el cálculo inicial de las probabilidades de sustitución entre aminoácidos. Poder cambiar un modelo de sustitución permite el elegir el modelo de sustitución. utilizar otra de estas matrices, realizando una heuristica diferente, otro calculo y asi poder ajustarlo segun el tipo de input/output buscado.
Bootstrap es unn tipo de medidas que permite evaluar el nivel de confianza de las ramas que se encuentran en un árbol filogenético, proporcionando fiabilidad y robustez. Es el método más utilizado para parsimonia y máxima verosimilitud.El mismo se basa en la generación de una matriz de datos cuyas columnas se van transformando de forma aleatoria y a partir de cada una de las matrices resultados, crear un árbol filogenético, contando al final en cuantos de ellos aparece la secuencia a estudiar. Finalmente indica el porcentaje de veces en que cada nodo del árbol se presentó en las matrices remuestreadas. Al final todos estos árboles se representan en uno consenso donde aparecen los porcentajes de la proporción de cada réplica. Así, si una rama presenta más del 50% quiere decir que ésta es fiable. 
