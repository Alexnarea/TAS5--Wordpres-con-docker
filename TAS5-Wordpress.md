
# TAS5-Wordpress con Docker 
## 1. Titulo
Despliegue de un Sitio WordPress con Contenedores Docker Usando Comandos CLI
## 2. Tiempo de duración
El tiempo fue de 120 minutos. 
## 3. Fundamentos:

## Redes Docker 

Las redes Docker configuran las comunicaciones entre contenedores vecinos y servicios externos. Los contenedores deben estar conectados a una red Docker para recibir conectividad de red. Las rutas de comunicación disponibles para el contenedor dependen de sus conexiones de red (Docker Networking - Basics, Network Types & Examples, n.d.).

La red de contenedores se refiere a la capacidad de los contenedores de conectarse y comunicarse entre sí o con cargas de trabajo que no sean Docker. Los contenedores tienen la red habilitada por defecto y pueden realizar conexiones salientes. Un contenedor no tiene información sobre el tipo de red al que está conectado ni si sus pares también son cargas de trabajo de Docker. Un contenedor solo ve una interfaz de red con una dirección IP, una puerta de enlace, una tabla de enrutamiento, servicios DNS y otros detalles de red. Esto es así, a menos que el contenedor utilice el nonecontrolador de red (Redes | Documentación de Docker, n.d.).

<img src="./redes-container/redes.png" alt="drawing0" width="500"/>

## MySQL 

La forma tradicional de ejecutar una base de datos MySQL es instalar los paquetes MySQL y las aplicaciones simplemente tendrían que conectarse al puerto de escucha. La mayoría de las tareas de administración, como el ajuste de la configuración, las copias de seguridad, la restauración, la actualización de la base de datos, el ajuste del rendimiento y la resolución de problemas, deben ejecutarse en el propio host de la base de datos. Se espera que haya varios puertos accesibles para la conexión, por ejemplo, el puerto TCP 22 para SSH, el TCP 3306 para MySQL o el UDP 514 para syslog (Contenedores Docker de MySQL: Conceptos Básicos | Variousnines, n.d.).

En un contenedor, piense en MySQL como una sola unidad que solo sirve contenido relacionado con MySQL en el puerto 3306. La mayor parte de las operaciones se realizan en este único canal. Docker funciona de maravilla empaquetando su aplicación/software en una sola unidad, que luego puede implementar en cualquier lugar siempre que el motor Docker esté instalado. Espera que el paquete o la imagen se ejecute como un único proceso por contenedor. Con Docker, el flujo sería que usted (o alguien más) cree una imagen de MySQL con una versión y un proveedor específicos, la empaquete y la distribuya a cualquiera que desee ejecutar una instancia de MySQL rápidamente (Contenedores Docker de MySQL: Conceptos Básicos | Variousnines, n.d.).


<img src="./redes-container/sql.png" alt="drawing0" width="500"/>

## PhpMyAdmin

Sin una interfaz de usuario, solo se puede interactuar con MySQL mediante la Terminal (o PowerShell y el Símbolo del sistema, según el sistema operativo). phpMyAdmin soluciona este problema al ser una aplicación web portátil de código abierto que actúa como herramienta de administración para MySQL. Una alternativa sería MySQL Workbench , pero requiere instalación en el equipo local y anula el propósito de usar Docker. Docker es una herramienta que empaqueta software en contenedores, independientemente del sistema local. Docker se utilizó para ejecutar MySQL y phpMyAdmin en el equipo local sin necesidad de instalación, y puede usarse para empaquetar toda la configuración en el futuro (MySQL y PhpMyAdmin En Docker - Ciencia de Datos de Pila Completa, n.d.).


<img src="./redes-container/php.png" alt="drawing0" width="500"/>

## 4. Conocimientos previos.
   
Para realizar esta practica el estudiante necesita tener claro los siguientes temas:
- Comandos de Docker.
- Conceptos de contenedores y volumenes.
- Conceptos básicos de bases de datos.
- Conocimientos de acceso web y puertos.

## 5. Objetivos a alcanzar

- Crear una red.
- Crear un volumen para wordpress.
- Crear un volumen para mysql.
- Crear un contenedor para mysql.
- Crear un contenedor para phpmyadmin.
- Crear un contenedor de wordpress.

## 6. Equipo necesario:
  
- Computador.
- Docker funcionando.
- Navegador web.

## 7. Material de apoyo.
   
- Documentación de Docker
- Guía de asignatura.
- Cheat Sheet de comandos Docker.
- Documentación oficial de MySQL, phpMyAdmin y Wordpress.
- Videos tutoriales.

## 8. Procedimiento

### Pasos 

1. Crear un red personalizada.

Figura 8-1 Creación de la red personalizada 

<img src="./redes-container/r1.PNG" alt="drawing0" width="500"/>

2. Crear un volumen para wordpress.
3. Crear un volumen para mysql.


Figura 8-3 Creacion de los volumenes para wordpress y mysql.

<img src="./redes-container/r3.PNG" alt="drawing0" width="500"/>


4. Crear un contenedor para mysql.
   
Figura 8-4 Creacion del contenedor para mysql.

<img src="./redes-container/r4.PNG" alt="drawing0" width="500"/>

5. Crear un contenedor para phpmyadmin.

Figura 8-5 Configuracion y creacion de la base de datos en la interfaz de phpMyAdmin.


<img src="./redes-container/r5.PNG" alt="drawing0" width="500"/>


## 9. Resultados esperados:
    
Al finalizar la práctica, se logró cumplir exitosamente los objetivos planteados. Se desplegó correctamente un contenedor de base de datos MySQL, configurando las credenciales de acceso (root/admin) y exponiendo el puerto 3307. Mediante la creación de una red personalizada, se facilitó la comunicación entre los contenedores de MySQL y phpMyAdmin, evitando conflictos de puertos y garantizando la resolución de nombres de servicio.

Desde phpMyAdmin, accedido a través del navegador en el puerto 8081, se pudo gestionar el servidor MySQL y crear de forma gráfica una base de datos de prueba, verificando así la conectividad y funcionamiento del sistema. Durante el proceso se aplicaron comandos esenciales de Docker como ``docker network create``, ``docker network connect``, y se comprendió la importancia de las variables de entorno para la configuración de servicios. Todo el desarrollo de la práctica fue documentado con capturas de pantalla que evidencian la creación de la red, el despliegue de los contenedores, la configuración de acceso y la creación exitosa de una base de datos de prueba desde phpMyAdmin.

<img src="./redes-container/resultado.PNG" alt="drawing0" width="500"/>


## 10. Bibliografía
    
- Contenedores Docker de MySQL: Conceptos básicos | Variousnines. (n.d.). Retrieved April 25, 2025, from https://severalnines.com/blog/mysql-docker-containers-understanding-basics/
- Docker Networking - Basics, Network Types & Examples. (n.d.). Retrieved April 25, 2025, from https://spacelift.io/blog/docker-networking
- MySQL y phpMyAdmin en Docker - Ciencia de datos de pila completa. (n.d.). Retrieved April 25, 2025, from https://andrewyewcy.com/MySQL-and-phpMyAdmin-on-Docker/
- Redes | Documentación de Docker. (n.d.). Retrieved April 25, 2025, from https://docs.docker.com/engine/network/


