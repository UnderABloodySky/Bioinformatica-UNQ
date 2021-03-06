# Bioinformatica-UNQ

## Tp 1 - Introducción a la Bioinformática

#### Integrantes Tp1: ####

*Facundo Pacheco

*Horacio Valenzuela

#### RETO I: ¿Podrías buscar un ejemplo de macromoléculas que almacenen información sobre la ‘identidad’ de un organismo dado?  

Un ejemplo de esto son los acidos nucleicos (el *ácido desoxirribonucleico* - o ADN - y el *ácido ribonucleico* - o  ARN-). 
La estructura de doble hélice del ADN proporcionó respuestas al tema de la herencia, predijo la autorreplicación del material genético y la idea de que la información genética estaba contenida en la secuencia de las bases que lo conforman. El ADN contiene las instrucciones que determinan la forma y características de un organismo y sus funciones.

![Meme - Daenerys - ADN/ARN](https://github.com/pache0015/Bioinformatica-UNQ/blob/master/TP%20-%201/img/ADN%7CARN.jpg)
 
      
        
#### RETO II: Proponé una forma de expresar la información contenida en la estructura primaria de las proteínas usando tipos de datos de los lenguajes de programación que conocés.

Siendo simplistas, se podria expresar la informacion contenida en la estructura primaria de las poteinas usando cualquier estructura que sea iterable; amerita mencionar la simpleza de un String o cadenas de caracteres. Teniendo en cuenta que para este trabajo se eligío el lenguaje de programación ___Haskell___, una posible forma de modelar dicha estructura primaria sería con los datas especificados en el archivo: [TP-1.hs](https://github.com/pache0015/Bioinformatica-UNQ/blob/master/TP%20-%201/tp-1.hs).
  
    
      
        
          
#### RETO III: ¿ En qué tipo de datos podrías expresar la información de la estructura terciaria proteica?
La informacion de la estructura terciaria proteica  se podría expresar de varias maneras distintas, dependiendo el nivel de dificultad que se quiera imprimir en la calidad del código. Una forma simple de verlo es como una listas de listas. Por cada aminoácido tener una lista donde en principio esté la estructura secundaria definida y condicionada previamente por las bases representadas y otra lista con las coordenadas para saber dónde graficarlo en función del espacio (o bien cualquier estructura que permita aglomerar una serie de estructuras o datos relacionados, como puede ser una ___n-tupla___ o similar). Otra forma de pensarlo, quizas un poco mas compleja, es atraves de una estructura arbolea, como puede ser un grafo, donde se podria incluir mucha más informacion estructural. Para ganar un conocimiento profundo al respecto, en el [TP-1.hs](https://github.com/pache0015/Bioinformatica-UNQ/blob/master/TP%20-%201/tp-1.hs) se podra encontrar una propuesta utilizando nuevamente ___Haskell___ y un par de funciones pertinentes.
  
    
      
        
          
          
#### RETO IV: Rosalind Franklin es una científica muy relevante, que tuvo menos reconocimiento del merecido. ¿Cuáles fueron sus contribuciones en este campo? ¿Qué nos cuenta su historia acerca del mundo de la ciencia?
 
 ![Meme - Rosalind](https://github.com/pache0015/Bioinformatica-UNQ/blob/master/TP%20-%201/img/rosalinda.jpg)
  
Sus contribucioines en este campo fueron la clave para el entendendimiento de la estructura del ___ADN___, mediante las fotos que pudo tomar utilizando la técnica de difracción de Rayos X, en la cual era una experta a nivel mundial.

![Foto 51 - 52](https://github.com/pache0015/Bioinformatica-UNQ/blob/master/TP%20-%201/img/Figura-3-Fotografias-51-y-52-del-ADN-de-Rosalind-Franklin-Forma-hidratada-B-foto-51.png)

En cuanto a lo que nos cuenta su historia acerca del mundo de la cienca puede verse a través de varias aristas, lamentablemente todas ellas negativas. En una primer vision, la más inmediata, resalta lo machista de la época y el poco lugar que tenian las mujeres en los ámbitos científicos/academicos por muy buenas que fueran en sus areas de competencia,ni por más aportes que hagan en nombre de la ciencia, como es el caso de Rosalind, entre otras muchas. No le dio el prestigio o importancia que merecían, como bien lo explica Nadia Chiaramoni,profesora de la UNQ e investigadora del Conicet:

[!["Un cerebro mas liviano"](http://img.youtube.com/vi/UR7AV6nXpD0/0.jpg)](https://www.youtube.com/watch?v=UR7AV6nXpD0 "Nadia Chiaramori - Un cerebro más liviano- Prof. UNQ.TEDx")
      
        
        
#### RETO V: Proponé en pseudocódigo un programa que prediga la estructura secundaria que adoptará cada residuo de la secuencia proteica dada, especificandola como H (si es una hélice), B (si es una hoja beta plegada) y L (si es un bucle o loop).
Ver una posible solución en el [TP-1.hs](https://github.com/pache0015/Bioinformatica-UNQ/blob/master/TP%20-%201/tp-1.hs).
___Nota___: Para predecir la estructura secundaria que adoptará cada residuo de la secuencia proteica dada, a traves de una serie de datos que se obtienen de analizar la secuencia y la estructura de amplios conjuntos de proteínas con estructura conocida y se establece una correlación entre las características estructurales y la secuencia para determinar cuál es la
probabilidad de que un determinado residuo adopte un tipo de estructura secundaria u otro. Este calculo devengará en un porcentaje que determina la probabilidad de que se adopte o bien una hélice, una hoja beta plegada o un loop. Como puede verse en la siguiente tabla:

![tabla - Estructura secundaria](https://github.com/pache0015/Bioinformatica-UNQ/blob/master/TP%20-%201/img/tabla.jpg)

Esto podria pensarse como: (asumiendo que la lógica de las probabilidades esta abstraida en la función problabilidad_ __estructura__). Finalmente, a la union de las distintas cadenas secundarias resultante, se le aplica una funcion que determine finalmente la posicion real en el espacio de la estructura resultando, entendiendo que las posibilidades de que un residuo adopte cierta forma no es información suficiente como para determinar en una forma tan "lineal" la estructura secundaria final.

~~~~
analisis{
    Por cada ___residuo___ en ___secuencia_proteica___ {
        Si probabilidad_helix(___residuo___){
            resultaddo = retorna H (informacion_de(___residuo___)) + residuos en secuencia
        } 
        Sino{
            Si (){
                resultaddo = retorna B (informacion_de(___residuo___))  + residuos en secuencia
            }
            Sino{
                resultaddo = retorna L (informacion_de(___residuo___)) + residuos en secuencia
            }
    }
    formaFinal(resultado)
}
~~~~

Por simplicidad, en el modelo propuesto, la forma de resolver dicha situacion fue priorizando, tomando dichos valores deforma deterministica, sin recurrir en las probabilidades. Se intenta priorizar la idea fundamental por sobre la implementación, como motivación para el acercamiento a un tema nuevo. 
 
    
- PREGUNTAS DISPARADORAS: ¿Qué inputs tendría tu programa? ¿De qué modo se te ocurre configurar el output?

 En este ejemplo [TP-1.hs](https://github.com/pache0015/Bioinformatica-UNQ/blob/master/TP%20-%201/tp-1.hs) es un aminoácido el input que recibe la función que evaluará la qué estructura secundaria que se tendrá. Si bien su complejidad es muy baja ya que solo retorna el tipo más problable de estructura secundaria, siendo posible Alpha Hélice, Beta Plegada o Loop. No se tuvo en cuenta las probabilidades de que un mismo aminoácido pueda llegar a tomar otra estructura que no sea la más probable para si mismo.
    
     
#### RETO VI: ¿Qué hace distintos a dos individuos de una especie? Propone una forma de corroborar tu respuesta realizando un diagrama de un posible método computacional para dicho fin.
  

Todos  los organismos de una determinada especie comparten ciertas generalidades. Independientemente a ello, cada individuo posee caracteristicas particularidades. Esto tiene el nombre de variabilidad y se origina por mutaciones, recombinaciones, etc. En definitiva, esas diferencias va a estar dada por los ___genes___ en el ___ADN___ y la información en ellos.
    
    
- PREGUNTAS DISPARADORAS: ¿Qué información deberías tener? ¿De qué modo deberías expresar dicha información para el análisis?

La información que se deberia tener a priori es una muestra genetica de ambos individuos.
