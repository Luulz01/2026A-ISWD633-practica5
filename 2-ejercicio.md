# Ejercicio
Configurar SonarQube utilizando Docker Compose, para esto necesitas dos servicios:
- Servicio: SonarQube
- Desde el host es necesario acceder a SonarQube por lo que necesitas mapear el puerto correspondiente.
- Servicio: PostgreSQL (existen otras opciones: Microsoft SQL Server, Oracle)
- Coloca un healtcheck para cada uno de los servicios.
- Los dos servicios deben pertenecer a una red de tipo bridge
- Investiga cuáles son los volúmenes necesarios para cada servicio
- Investiga cuáles son las variables de entorno para que los servicios funcionen de manera adecuada.
  
# Una vez creado tu archivo .yaml realiza la respectiva prueba 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/788be276-0168-4a02-985e-561b3fba7883" />

<img width="1769" height="542" alt="{6270B8B8-0E0C-4917-AD9C-AE17AD3EAB78}" src="https://github.com/user-attachments/assets/542554b4-e3bf-4893-95ee-e1d69b0b49b3" />

# COMPLETAR CON UNA CAPTURA DE PANTALLA LUEGO DE EJECUTAR EL ARCHIVO
<img width="1341" height="390" alt="{FCA09235-C7CE-4B9D-A16E-BA92C61D4612}" src="https://github.com/user-attachments/assets/29667b65-5816-416b-906b-d42375b949f4" />

**Comando: docker compose ps**
<img width="1347" height="190" alt="{10746F15-DB6C-4F12-90FB-4B17569439B7}" src="https://github.com/user-attachments/assets/d841e067-a5f0-4c32-901a-f6e57e334032" />


# ACCEDER A LOCALHOST:puertoDefinido para ingresar a SonarQube
Acceso: http://localhost:9000
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/987b9c78-a937-43fe-893a-6db44b188ddb" />

<img width="1773" height="791" alt="{029922B6-8ECC-4AE7-8524-5577B4D68721}" src="https://github.com/user-attachments/assets/88cc5d7e-2011-4d97-a25c-dd1e660e5ae0" />

<img width="1896" height="950" alt="{EC9787AF-2408-4DB1-B37B-978507ED3ADC}" src="https://github.com/user-attachments/assets/6431a8c9-43f9-45e6-bb0c-3bf0cd4f557f" />
