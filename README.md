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


## Instalacion nginx 
✨[Descargar](https://nginx.org/en/download.html)✨
- Descargar en dico C, y pegar el proyecto en la carpeta de nginx y remplazar el archivo nginx.conf por el que viene con el proyecto

## Dependencias
- winston: npm install winston
- armery: npm install -g artillery
