### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:15-alpine3.21

Debido a que el contenedor Postgres va a trabajar de forma interna (No tendra conexion directa con el host), es necesario definir un puente para conectar ambos contenedores.

Usamos el siguiente comando para crear la red interna.

```
docker network create mi_red_interna
```

<img width="806" height="78" alt="image" src="https://github.com/user-attachments/assets/4a11dc27-8512-47a8-b4a3-6ae00b38ae71" />

Ahora si se puede crear el contenedor sin exponer los puertos.

```
docker run -d --name postgres_interno -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=admin123 -e POSTGRES_DB=mi_base --network mi_red_interna postgres:15-alpine3.21
```

<img width="1457" height="439" alt="image" src="https://github.com/user-attachments/assets/8f3ff556-1bdf-4d31-a1cb-223fb0504910" />

### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4

```
docker run -d --name pgadmin_interno -e PGADMIN_DEFAULT_EMAIL=admin@demo.com -e PGADMIN_DEFAULT_PASSWORD=admin123 -p 8080:80 --network mi_red_interna dpage/pgadmin4
```
<img width="1458" height="505" alt="image" src="https://github.com/user-attachments/assets/8e8a35b1-aa7f-41c7-9d77-31161d7f4a2c" />


# COMPLETAR

La figura presenta el esquema creado en donde los puertos son:
- a: 8080
- b: 80
- c: 5432 puerto interno de pgadmin

![Imagen](esquema-2-ejercicio.PNG)

## Desde el cliente
### Acceder desde el cliente al servidor postgres creado.
# COMPLETAR CON UNA CAPTURA DEL LOGIN

<img width="1913" height="1095" alt="image" src="https://github.com/user-attachments/assets/44405e9d-47db-4d73-80a3-52718fb3506f" />

<img width="1919" height="1046" alt="image" src="https://github.com/user-attachments/assets/9293d598-93e3-47a8-820b-0c0103a19b22" />

<img width="868" height="676" alt="image" src="https://github.com/user-attachments/assets/8c090f13-7a25-48c2-b148-eb2698019143" />


### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.

<img width="1919" height="955" alt="image" src="https://github.com/user-attachments/assets/f4034ad5-6756-4acc-b4fe-01d04b7d4f03" />


## Desde el servidor postgresl
### Acceder al servidor
### Conectarse a la base de datos info
# COMPLETAR
### Realizar un select *from personas

<img width="677" height="456" alt="image" src="https://github.com/user-attachments/assets/4f75cc28-0d88-490a-9411-c33e956e7fb4" />

# AGREGAR UNA CAPTURA DE PANTALLA DEL RESULTADO

<img width="990" height="988" alt="image" src="https://github.com/user-attachments/assets/333b355f-3218-489b-8db4-3d5303d85f0e" />

