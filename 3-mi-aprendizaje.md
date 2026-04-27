# MI APRENDIZAJE
**Nombre:** Lizeth Hernández

En esta práctica se implementó Docker Compose, lo que permitió definir y gestionar múltiples contenedores de manera estructurada en un solo archivo YAML. Comprendí cómo automatizar la creación y ejecución de servicios interdependientes como MySQL y WordPress, facilitando el despliegue de aplicaciones completas con un solo comando.

Además, reforcé el uso de variables de entorno para configurar servicios, así como la importancia de mantener coherencia entre ellas para garantizar la correcta comunicación entre contenedores. Otro aspecto importante fue la implementación de healthchecks, que permiten verificar el estado de los servicios y asegurar que dependencias como WordPress solo se inicien cuando la base de datos esté completamente operativa. 

### Conocimientos previos
- Creación y ejecución de contenedores con Docker.
- Uso de imágenes y comandos básicos como docker run, docker ps y docker rm.
- Uso de redes para comunicación entre contenedores.
- Configuración de variables de entorno en contenedores.
- Mapeo de puertos para exponer servicios al host.


### Conocimientos adquiridos después de la práctica
- Uso de Docker Compose para definir aplicaciones multi-contenedor.
- Configuración de servicios mediante archivos YAML.
- Implementación de variables de entorno para conexión entre servicios.
- Implementación de healthchecks para verificar el estado de los contenedores.
- Uso de depends_on con condición service_healthy para controlar el orden de inicio.


### Comandos
- **docker compose up -d:**
Ejecuta los servicios definidos en el archivo compose.yaml en segundo plano.
- **docker compose ps:**
Muestra el estado de los contenedores creados por Docker Compose.
- **docker compose down:**
Detiene y elimina los contenedores, redes y recursos creados.
- **docker compose up -d <servicio>:**
Permite levantar un servicio específico en caso de fallos.
- **docker logs <nombre_contenedor>:**
Muestra los registros de un contenedor para identificar errores.

### Cosas que realicé y aprendí
- Configuré dos servicios: MySQL y WordPress mediante Docker Compose.
- Establecí la comunicación entre contenedores usando una red personalizada.
- Implementé variables de entorno para conectar WordPress con la base de datos.
- Realicé el mapeo de puertos para acceder a WordPress desde el navegador.
- Configuré healthchecks para verificar el estado de cada servicio.
- Utilicé volúmenes nombrados para garantizar la persistencia de datos.
- Comprendí la importancia de la dependencia entre servicios usando depends_on.


### Problema
**1) Inconveniente con la versión imagen**

Durante la práctica de configuración de SonarQube con Docker Compose se presentó un inconveniente relacionado con la compatibilidad de versiones de las imágenes. Inicialmente se utilizó una versión de SonarQube que no era totalmente compatible con la versión de PostgreSQL definida en el archivo compose.yaml, lo que provocó errores en la conexión a la base de datos y fallos durante el arranque del contenedor.

<img width="1092" height="293" alt="{C4CF9CCC-DA88-4C56-BFF9-EA391D77C46D}" src="https://github.com/user-attachments/assets/8a27561b-164a-4d9d-8335-ff360909fb95" />

<img width="937" height="186" alt="{9A27E9A4-348F-4A9D-9F65-255048C7A750}" src="https://github.com/user-attachments/assets/0fb0e3b6-8521-409f-8c36-90254ef1f011" />


La solución consistió en investigar la documentación oficial y ajustar las versiones de las imágenes utilizadas, seleccionando combinaciones compatibles por ejemplo, SonarQube Community con PostgreSQL 15. Una vez corregido esto, los servicios lograron comunicarse correctamente y el sistema inició sin errores.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/788be276-0168-4a02-985e-561b3fba7883" />

<img width="771" height="644" alt="{FD9ACACD-D9CE-4770-B31C-EEB46798D848}" src="https://github.com/user-attachments/assets/c72a07ec-3c9d-4d2d-9055-e65cec3832e7" />


**2) Credenciales incorrectas**

Problema con las credenciales iniciales al iniciar en SonarQube, porque las credenciales primeras que se deben usar es admin/admin y luego configurar la contraseña que se desea.

<img width="1791" height="891" alt="{B92B8D36-7480-4C9E-85C4-93BC53F11986}" src="https://github.com/user-attachments/assets/51c79aa9-ae0c-44bc-89d5-767d74fc4da2" />


admin/admin - contraseña inicial

<img width="1773" height="791" alt="{029922B6-8ECC-4AE7-8524-5577B4D68721}" src="https://github.com/user-attachments/assets/cbb18078-06d7-479d-94a8-83b77d166625" />

<img width="1896" height="950" alt="{EC9787AF-2408-4DB1-B37B-978507ED3ADC}" src="https://github.com/user-attachments/assets/6431a8c9-43f9-45e6-bb0c-3bf0cd4f557f" />

### ¿Qué ventaja tiene Docker Compose frente a ejecutar contenedores manualmente?

Docker Compose permite definir y gestionar múltiples contenedores en un solo archivo, facilitando la automatización, organización y replicación de entornos. A diferencia de ejecutar contenedores manualmente con docker run, Compose reduce errores, mejora la escalabilidad y permite levantar toda la aplicación con un solo comando.

### Conclusión

En esta práctica aprendí a utilizar Docker Compose para dirigir múltiples contenedores, comprendiendo cómo definir servicios, redes, volúmenes y dependencias en un archivo YAML. Además, reforcé la importancia de una correcta configuración de variables de entorno y healthchecks para garantizar el correcto funcionamiento de aplicaciones distribuidas.
