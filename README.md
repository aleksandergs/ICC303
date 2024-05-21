Practica #1 multiplicando matrices con MPI en java:
En el codigo que se puede encontrar en src/Matrix/MatrixMul.java se encuentra detallado la funcion de cada parte del codigo. Debido a que el codigo hace uso de la libreria MPJ express para poder correrlo se necesita descargarlo y agregar mpj.jar como dependencia del projecto en el IDE usado (en mi caso IntelliJ), tambien se necesita establecer la variable de entorno MPJ_HOME a la ubicacion de mpj y en la configurarion de corrida agregar como argumentos de ejecucion "-jar \$MPJ_HOME\$\lib\starter.jar -np N" donde N es el numeros de procesos/hilos que se quiere que mpi utilice en el programa.

**Es muy importante que para una cantidad x de procesos que queramos usar las matrices nxn que utilicemos sean de la forma x<n y donde n es un multiplo de x** (en otras palabras queremos que el tamaño de las matrices sea un numero mayor y multiplo del numero de procesos, esto debido a la forma en que se reparte el trabajo entre los procesos).

se comprobo que los resultados fueran los mismos usando los procesos paralelos al igual que con uno solo y com matrices de distintos tamaños de matrix

![image](https://github.com/aleksandergs/ICC303/assets/53494540/c34097b3-a47e-486d-8543-4a1aad98fee4)
![image](https://github.com/aleksandergs/ICC303/assets/53494540/33b420e7-1e25-441f-9014-6f44d303f399)
![image](https://github.com/aleksandergs/ICC303/assets/53494540/9ed1430e-f6d9-4b6b-8a1f-66b471a13940)


