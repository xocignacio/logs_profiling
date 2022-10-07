# Prueba de desempeño y estres

## Rutas de prueba
✨[Prueba de logs con fn de suma 4 + 4](http://localhost:8080/suma/4/4)✨


## LOGS
-  Logs realizados con libreria winston (debug y error con una funcion de suma como prueba) registra actividad de la aplicacion => soporte para multiples transportes
 src_logs/app.js => funcion de suma por params para generar logs 

```sh
 src_logs/app.js => funcion de suma por params para generar logs 

```


## ARTILLERY 
> Artillery es una libreria nativa de node, para realizar pruebas de carga, simula procesos, como numeros de usuarios y peticiones que buscan comprobar el comprotamiento del server bajo ESTRES
- Comando de consola para prueba de carga => artillery quick --count 50 -n 40 http://localhost:8080?max=10000 > resultFork.txt   
(simula 50 usuarios que envian 40 peticiones) y genera un archivo que puedo nombrar como quiera con toda la estadistica 
- Sin profiling mide que tanta carga soporta el servidor y cuanto tarda en procesarlo
- Server corriendo en modo fork en localhost8080 aunque puedo pasar por argumento otra direccion como 8081 y el metodo CLUSTER para tener 2 diferentes servers y comparar sus rendimientos bajo una prueba de estres

```sh
  src_artillery/app.js => funcion de numeros primos para evaluar con artillery su comportamiento en modo fork y se puede pasar por argumento modo cluster

```

## PROFILING
>  Es la investigación del comportamiento de un programa usando información reunida desde el análisis dinámico del mismo.
-  El objetivo es averiguar el tiempo dedicado a la ejecución de diferentes partes del programa para detectar los puntos problemáticos y las áreas donde sea posible llevar a cabo una optimización del rendimiento (ya sea en velocidad o en consumo de recursos).
1 - prender servidor en modo profiler :
```sh
 node --prof server.js

```
- esto genera un archivo insolate-000,que esta encriptado,por lo cual le cambio el nombre al archivo
para decodificarlo y que sea mas facil de leer la informacion 
2- Modificar archivo 

```sh
node --prof-process "nombre archivo" > resul_prof-final

```

node --prof-process "nombre archivo" > resul_prof-final

## CHROME INSPECT

- 1 prender servidor con node --inspect server.js
- 2 Visitar chrome inspect => chrome://inspect
- 3 abrimos el dev tools
- 4 Se nos abre una nueva ventana, y vamos a la pestaña profiler. Allí, cliqueo en el botón de start.
- 5 Una vez hecho esto, puedo volver a la consola y correr nuevamente los comandos del test de carga artillery que mencionamos anteriormente. Para los procesos   
  bloqueante y no bloqueante.
  pero sin el input salida de txt ya que lo leo en el browser
- 6 Una vez que finaliza, ponemos el botón stop en el navegador, y nos muestra algo como esto, con la misma información que los archivos vistos anteriormente
- 7 Si vamos a “run” y luego desplegamos también el proceso que se nos abre, podemos ver, mirando a la derecha que en el archivo server.js línea 32 tenemos un proceso bloqueantes.
Podemos entonces hacer click sobre eso (server.js:32).
Con esto, se nos abre la vista del código, junto con el tiempo en milisegundos que demoró esa función.
Entonces podemos ver los milisegundos de cada función y ver las que están demorando la ejecución de la aplicación.


## Dependencias
- Winston: npm install winston
- Artillery: npm install -g artillery
