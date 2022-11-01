# Proyecto_1 - Sharks1

<img width="564" alt="Captura de Pantalla 2022-10-31 a las 20 04 01" src="https://user-images.githubusercontent.com/115650089/199089140-c8215f38-2ab7-43fe-8485-eec6b120fc5f.png">

En este proyecto, he limpiado una base de datos que contiene registros de ataques de tiburón. Los pasos que he seguido son los siguientes:

1. Empecé importando las librerías necesarias para poder utilizar sus funciones. Estas son Pandas y Numpy.

2. Después, cargué el archivo que contenía la base de datos de ataques y le hice una copia, para mantener el original. 

EXPLORACIÓN 

1. Una vez cargado el archivo, exploré la base de datos. Miré las primeras líneas, la longitud, las columnas y los tipos de dato. Comenzamos con 25723 líneas y 24 columnas.

2. Observando los tipos de datos, vi que había varios valores nulos, por lo que saqué el porcentaje de los mismos para cada columna y, tras ver que había dos de ellas con más del 80% de valores nulos, las eliminé. Estas fueron 'Unnamed: 22' y 'Unnamed: 23'. 

3. Luego, me di cuenta que a partir de la última línea completa de la columna "Date", los datos empezaban a estar muy sucios y con varios valores nulos, por lo que borré todas las filas desde ese punto y me quedé con 6302. Después, cambié el resto de valores nulos por la palabra 'unknown'

4. Al ver los nombres de las columnas, me di cuenta de que varios tenían espacios. Les quité a todas los espacios y los puse en mayúscula, por una cuestiónn de estética. 

LIMPIEZA

1. Empecé por la columna de 'SEX'. Comprobé que todos los valores fueran 'M', 'F' o 'unknown', y para los que no fuera así, hice un bucle con la función replace() para arreglarlo. Esto pude hacerlo porque comprobé previamente todos los casos únicos y no eran demasiados. 

2. Cambié los nombres a las columnas "DATE" y "CASE NUMBER" a "CASE ID" y "DATE", respectivamente. De esta forma, podía conseguir una columna de fechas más limpia. En la columna "CASE ID", hice un bucle para rellenarla con un índice. Por otra parte, en la columna "DATE" creé una función con REGEX para quedarme únicamente con las fechas en el formato num.num.num

3. Para la columna "COUNTRY", miré los valores únicos y creé una función con REGEX para quedarme únicamente con los nombres de los países.

4. Después, pasé a limpiar la columna de la edad. Para ello, creé una función en la que recogía mediante un patrón regex  los casos en los que hubiera hasta 5 números diferentes y sacaba una media. Además, metí varios condicionales donde indicaba que, si un tipo de String estaba dentro del valor, se me devolviera un número (adulto, adolescente).

5. La columna de "YEAR", simplemente la pasé a int para que el formato fuera un número entero.

6. En la columna de "ACTIVITY", utilicé una función en la que se pasaban varios patrones concretos de REGEX para ir capturando todos los términos que se referían a cada una de las actividades.  

7. Por último, en la columna fatal, aseguré que solamente hubiera 2 valores, 'Y' / 'N', además de los nulos.

CONCLUSIONES

Para finalizar, saqué dos tablas de doble entrada donde se comparaba la cantidad de casos por sexo y por país:


<img width="548" alt="Captura de Pantalla 2022-11-01 a las 9 38 04" src="https://user-images.githubusercontent.com/115650089/199192947-25381a74-c68b-41c4-8abf-53f12aa2d5a8.png">



<img width="159" alt="Captura de Pantalla 2022-11-01 a las 9 38 27" src="https://user-images.githubusercontent.com/115650089/199193008-81a0eccc-1f5d-4f18-9426-2f5a1abe9ab4.png">

