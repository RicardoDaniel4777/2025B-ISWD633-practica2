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
docker run --name contenedorMysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:8
```
<img width="1109" height="384" alt="image" src="https://github.com/user-attachments/assets/c0fc1798-a8aa-4c98-acb6-3fc9fcbdd0e2" />



### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# COMPLETAR
<img width="903" height="746" alt="image" src="https://github.com/user-attachments/assets/ae39e8ac-2eea-422a-b068-a60ba83467f2" />

De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es **(9300)**

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
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

