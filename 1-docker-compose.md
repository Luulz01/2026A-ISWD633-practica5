# Docker Compose
Es una herramienta que permite definir y gestionar aplicaciones Docker multi-contenedor de forma sencilla. Puedes usar un archivo YAML usuamente llamado compose.yaml para configurar los servicios de tu aplicación, como contenedores, redes y volúmenes, y luego iniciar toda la aplicación con un solo comando.

Docker Compose simplifica el proceso de definir la estructura de una aplicación con múltiples servicios y sus interacciones, lo que facilita el desarrollo, la prueba y el despliegue de aplicaciones complejas.

Un archivo YAML (YAML Ain't Markup Language) se forma utilizando una estructura de datos basada en texto. Para el archivo considerar:
## Indentación
YAML usa espacios para la indentación, no tabuladores.
La indentación indica jerarquía. Asegúrate de usar el mismo número de espacios para cada nivel de indentación.
## Claves y valores
Las claves y valores se separan por dos puntos seguidos de un espacio (:).

## Ejercicio
El archivo compose.yaml permitirá configurar dos servicios de acuerdo con el siguiente esquema:

![Ejercicio docker compose](imagenes/ejercicio-docker-compose.PNG)

### Revise el archivo archivo compose.yaml y complete solamente las partes que solicitan <valor>, para eso considerar:
- La clave **services** define los servicios (contenedores) que conforman tu aplicación. Cada servicio se describe con un nombre único y contiene configuraciones específicas como la imagen de Docker que debe usar, los volúmenes, las redes, las variables de entorno, y más. Para el ejercicio es necesario definir dos servicios: mysql-service y wordpress-service.

**mysql-service**
<img width="629" height="447" alt="{532F1876-A7CF-4395-8669-FCD90DF13C73}" src="https://github.com/user-attachments/assets/4a5e98da-97c6-400c-9492-6b662c134194" />

**wordpress-service**
<img width="389" height="282" alt="{D48237EA-7EDE-4330-9A04-DEE56EAA12CC}" src="https://github.com/user-attachments/assets/a549c8fc-35db-4a47-a706-64b000f469ff" />


- Es necesario configurar las variables de entorno para cada uno de los contenedores

**mysql-container**

<img width="372" height="141" alt="{7570B670-7509-450D-9BB1-D07C619AADA7}" src="https://github.com/user-attachments/assets/8d32d5ae-d297-4cbf-85c7-bd21e8bc47da" />


**wordpress-container**

<img width="366" height="194" alt="{9A6E4DA4-A4BE-4E36-B82F-30A818521B44}" src="https://github.com/user-attachments/assets/90b35516-b3d0-47fa-8849-8f15ddf9db1e" />

- Realizar el mapeo de puertos para Wordpress host:contenedor

<img width="323" height="113" alt="{8CD777F7-6912-4235-830D-2128CFEA8E34}" src="https://github.com/user-attachments/assets/82eb498a-b6db-464c-ac19-8b71182b4fac" />

- Healthcheck de cada uno de los servicios.
    - Línea 17 test: ["CMD", "mysqladmin", "ping", "-h", "localhost"] para verificar si el servidor MySQL está en funcionamiento y puede responder a las solicitudes de ping.
    - Línea 38 test: ["CMD", "curl", "-f", "http://localhost"] para verificar si un servidor HTTP en el contenedor está funcionando y respondiendo correctamente.
- La dependencia entre el servicio de wordpress y la base de datos, se indica en las líneas 44-46
  - depends_on: Establece dependencias entre servicios. El servicio actual **wordpress-service** depende del servicio **mysql-service**. Podemos usar los nombres directamente ya que ambos contenedores pertenecen a la red de tipo bridge.
  - condition: service_healthy significa que el servicio actual solo se iniciará después de que el servicio mysql-service esté en un estado saludable, es decir, después de que pase su healthcheck.
- Línea 43 es necesario que el wordpress-container se encuentre disponible en todo momento, defina una política de reinicio adecuada para esto

<img width="482" height="238" alt="{47ADC68C-A62F-4A75-8C04-2529585630DA}" src="https://github.com/user-attachments/assets/ac112fc5-0921-42c6-9afa-8979622e7aee" />

- wordpress-vol y mysql-vol son volúmenes nombrados.
<img width="340" height="69" alt="{AA0B45B7-6A0F-492D-88DF-261307B64C6E}" src="https://github.com/user-attachments/assets/181fd91d-3b48-4421-a117-75b2e3335558" />

<img width="347" height="82" alt="{3CD7D859-CEC3-44F1-B3F5-10FE5A67C35E}" src="https://github.com/user-attachments/assets/9239e1f9-927e-4a61-9e04-078b082dadd5" />

### Ejecutar Docker compose
Este comando descargará las imágenes necesarias, creará y ejecutará los contenedores según lo definido en el archivo compose.yaml
Para ejecutar en modo "detached" (en segundo plano) se agrega la opción -d:
```
docker compose up -d
```

**Descarga archivo compose.yaml**
<img width="714" height="321" alt="{1ED8518B-48A4-42A1-9608-EA2B9779BC06}" src="https://github.com/user-attachments/assets/b09c79d5-5a63-491e-94ae-04daaf8f8224" />


### Ejecutar Docker compose para servicios que no se crearon correctamente
Si algún servicio no se creó correctamente se puede usar
```
docker compose up -d <nombre servicio>
```

### Listar contenedores en ejecución que se crearon por docker compose
```
docker compose ps
```
### COMPLETAR CON UNA CAPTURA DE PANTALLA DEL LISTADO DE LOS CONTENEDORES EN EJECUCIÓN

### Detener y eliminar los contenedores definidos en el archivo
```
docker compose down
```
