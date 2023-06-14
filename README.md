# COLGRUPO2
Repositorio CFTCCENCO
El siguiente código, define un programa en C++, que lee dos ficheros de texto en forma automática para generar una solución. Para los efectos didácticos de este trabajo colaborativo y como grupo hemos optamos por la herramienta web “www.Paiza.io”, un completo editor de código online. Una fascinante herramienta para estudiantes y entusiastas de la programación, que deseen crear código, editarlo y compilarlo sin necesidad de instalar pesados softwares en sus dispositivos aparte del navegador, incluso en Android.
El primer item a contestar requiere que se genere de forma manual dos ficheros con la información a manipular obtenidos del texto a analizar. Para nuestros criterios, optamos por dos estructuras organizativas, una bidimensional o matriz de 12 filas por 3 columnas denominado “Temperatura.txt” y un arreglo de 36 casillas nombrado “Agua_caida,txt” para las soluciones a las preguntas: ¿Cantidad de agua caída en Chile en mm?; Temperatura (°C) promedio por cada trimestre (agrupación de 4 meses) en Chile y Señalar que ciudad tuvo la temperatura más alta y baja en el 2022.
El editor web recibe por entrada estándar la matriz de 12 filas x 3 columnas en texto plano, el código divide la matriz en 3 partes iguales, grupos de cuatro meses a especificación del docente, y devuelve el promedio de cada parte denominados “Trimestres” por separado, almacenando los datos en las variables simples llamadas: “primer_trimestre”, “segundo_trimestre” y “tercer_trimestre” respectivamente. Luego muestra esas variables por la salida estándar con los mensajes: “Promedio primer trimestre”, “Promedio segundo Trimestre” y “Promedio tercer trimestre” respectivamente. 
Luego se ingresan los datos del segundo archivo denominado “Agua_caida.txt” con el arreglo de 36 casillas, los suma y almacena el resultado en una variable tipo int llamada “precipitaciones” y lo muestra en pantalla junto con el mensaje “Cantidad de agua caída “precipitaciones” mm”.  
Por último, crea dos variables tipo entero llamadas: “tmax” y “tmin”, con los valores 28 y 1 respectivamente y los muestre en pantalla junto al siguiente menaje: "La Temperatura máxima fue en Santiago con “tmax” °C", y "La Temperatura mínima fue en Puntarenas con “tmin” °C".
El docente especifica que no es necesaria interacción con el usuario, lo que implifica bastante el código.
Nota1: Para ejecutar este código, se debe copiar el código fuente descrito y pegarlo en la interfaz web del editor online.
Nota2: Para el correcto funcionamiento del código, se deben ingresar en texto plano por el campo de entrada primero lo datos de la matriz y luego separado por un espacio en blanco, los datos del vector. 
URL: https://paiza.io.

Código Fuente:
1.	#include <iostream>
2.	int main() {
3.	int matriz[12][3];
4.	int arreglo[36];
5.	int primer_trimestre = 0, segundo_trimestre = 0, tercer_trimestre = 0;
6.	int precipitaciones = 0;
7.	int tmax = 28, tmin = 1;

// Leer la matriz de 12x3
8.	for (int i = 0; i < 12; i++) {
9.	for (int j = 0; j < 3; j++) {
10.	std::cin >> matriz[i][j];
11.	}
12.	}

// Leer el arreglo de 36 datos y calcular la suma de las precipitaciones
13.	for (int i = 0; i < 36; i++) {
14.	std::cin >> arreglo[i];
15.	precipitaciones += arreglo[i];
16.	}

// Calcular el promedio de cada trimestre	
17.	for (int i = 0; i < 12; i++) {
18.	for (int j = 0; j < 3; j++) {
19.	if (j < 1) {
a.	primer_trimestre += matriz[i][j];
20.	} else if (j < 2) {
a.	segundo_trimestre += matriz[i][j];
21.	} else {
a.	tercer_trimestre += matriz[i][j];
22.	}
23.	}
24.	}




// Dividir la suma por la cantidad de elementos en cada trimestre
25.	primer_trimestre /= 12;
26.	segundo_trimestre /= 12;
27.	tercer_trimestre /= 12;

// Mostrar los promedios de los trimestres
28.	std::cout << "Promedio primer trimestre: " << primer_trimestre << std::endl;
29.	std::cout << "Promedio segundo trimestre: " << segundo_trimestre << std::endl;
30.	std::cout << "Promedio tercer trimestre: " << tercer_trimestre << std::endl;

// Mostrar la cantidad de precipitaciones
31.	std::cout << "Cantidad de agua caída: " << precipitaciones << " mm" << std::endl;

// Mostrar la temperatura máxima y mínima
32.	std::cout << "La Temperatura máxima fue en Santiago con " << tmax << " °C" << std::endl;
33.	std::cout << "La Temperatura mínima fue en Puntarenas con " << tmin << " °C" << std::endl;

34.	return 0;
35.	}


Archivos Fuente:
  
Archivo 1: Temperatura.txt.
  
28 25 10
27 24 11
26 23 10
22 20 7
19 17 4
16 15 2
15 14 1
16 15 2
18 17 4
21 19 7
24 22 9
26 24 10

Archivo 2: Agua_caida.txt:
0
5
10
15
20
25
30
25
20
15
10
5
2
5
10
15
20
25
30
25
20
15
10
5
20
15
10
12
25
35
40
35
25
18
15
12
