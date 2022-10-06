# Prueba de desempeño y estres

## Rutas
✨[Servidor 1](http://localhost:8080/)✨
✨[Servidor 2](http://localhost:8081/)✨

## Conceptos
-  Logs realizados con libreria winston (debug y error con una funcion de suma como prueba) registra actividad de la aplicacion => SOPORTE PARA MULTIPLES TRANSPORTES
-  Artillery es una libreria nativa de node, para realizar pruebas de carga, simula procesos, como numeros de usuarios y peticiones que buscan comprobar el comprotamiento del server bajo ESTRES

## Balancear la carga
Un solo servidor de origen, en una página con millones de visitantes diarios, no puede manejar todo el tráfico entrante.
El proxy inverso puede recibir el tráfico entrante antes de que llegue al servidor de origen. Si este está sobrecargado o cae completamente, puede distribuir el tráfico a otros servidores sin afectar la funcionalidad del sitio. Es el principal uso de los servidores proxy inverso.
Seguridad mejorada: Al ocultar el proxy inverso la IP del servidor de origen de un sitio web, se puede mantener el anonimato del mismo, aumentando considerablemente su seguridad. Al tener al proxy como intermediario, cualquier atacante que llegue va a tener una traba más para llegar al servidor de origen.


## Chrome inspect

- 1 prender servidor con node --inspect server.js
✨[Visitar chrome inspect](chrome://inspect)✨
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
- winston: npm install winston
- armery: npm install -g artillery
