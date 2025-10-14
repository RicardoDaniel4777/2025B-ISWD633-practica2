## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
# COMPLETAR
```
docker network create net-wp
```

<img width="721" height="82" alt="image" src="https://github.com/user-attachments/assets/51b1d262-977a-43a7-a51d-372af0bf90a9" />


### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias

```
docker run --name contenedorMysql --network net-wp -e MYSQL_ROOT_PASSWORD=my-secret-pw -e MYSQL_DATABASE=wordpress -e MYSQL_USER=wpuser -e MYSQL_PASSWORD=wppassword -d mysql:8
```
<img width="1197" height="136" alt="image" src="https://github.com/user-attachments/assets/3e19bb94-1371-44ac-9c91-62aa98f0bde7" />



### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# COMPLETAR
<img width="903" height="746" alt="image" src="https://github.com/user-attachments/assets/ae39e8ac-2eea-422a-b068-a60ba83467f2" />

De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es **(9300)**

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.

<img width="3819" height="1974" alt="image" src="https://github.com/user-attachments/assets/763ef89d-c0cf-4b99-ad71-d48ba6d19c79" />

# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN

Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.

### Eliminar el contenedor wordpress
# COMPLETAR

### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
# COMPLETAR

