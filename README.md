Practica #1 multiplicando matrices con MPI en java:
En el codigo que se puede encontrar en src/Matrix/MatrixMul.java se encuentra detallado la funcion de cada parte del codigo. Debido a que el codigo hace uso de la libreria MPJ express para poder correrlo se necesita descargarlo y agregar mpj.jar como dependencia del projecto en el IDE usado (en mi caso IntelliJ), tambien se necesita establecer la variable de entorno MPJ_HOME a la ubicacion de mpj y en la configurarion de corrida agregar como argumentos de ejecucion "-jar MPJ_HOME\lib\starter.jar -np N" donde N es el numeros de procesos/hilos que se quiere que mpi utilice en el programa.

**Es muy importante que para una cantidad x de procesos que queramos usar las matrices nxn que utilicemos sean de la forma x<n y donde n es un multiplo de x** (en otras palabras queremos que el tamaño de las matrices sea un numero mayor y multiplo del numero de procesos, esto debido a la forma en que se reparte el trabajo entre los procesos).

se comprobo que los resultados fueran los mismos usando los procesos paralelos al igual que con uno solo y com matrices de distintos tamaños de matrix

![image](https://github.com/aleksandergs/ICC303/assets/53494540/c34097b3-a47e-486d-8543-4a1aad98fee4)
![image](https://github.com/aleksandergs/ICC303/assets/53494540/33b420e7-1e25-441f-9014-6f44d303f399)
![image](https://github.com/aleksandergs/ICC303/assets/53494540/9ed1430e-f6d9-4b6b-8a1f-66b471a13940)

por ultimo usando una matrix de 1024 x 1024 se ejecuto 5 veces el programa con diversos numeros de hilos/procesos para comprobar el rendimiento:
1 proceso: 1771,	1380,	1330,	1357,	1280 : avg = 1423.6 ms\n
2 procesos: 864,	825,	877,	868,	854 : avg =	857.6 ms
4 procesos: 600,	640,	570,	600,	622 : avg = 606.4 ms
8 procesos: 549,	505,	544,	526,	511 :	avg = 527 ms
16 procesos: 500,	548,	694,	503,	594 : avg =	567.8 ms

como se puede aoreciar, en este ejemplo especifico la ventaja del paralelismo disminuye drasticamente apartir de 4 procesos y entre 8 y 16 hay un incremento en el tiempo que se toma probablemente causado por al gun overhead que realice la libreria mpi por cada proceso.





