# COMPLETAR  

## Conocimientos de antes y después de realizar la práctica

Antes de realizar la práctica tenia una vaga idea de lo que eran los contenedores, mis conceptos se confundian al pensar que docker era por si solo un contenedor, ahora me doy cuenta de que simplemente es una plataforma que permite crear, ejecutar y gestionar dichos contenedores, aunque no sea la única, existen otras más como podman o kubernetes.

Una vez completada ambas prácticas, he logrado conocer como funciona cada parte que conforma docker. Como por ejemplo:
1. Imagen -> Es simplemente una plantilla inmutable que contiene el sistema de archivos y dependencias.
2. Contenedor -> Es una instancia en ejecución de una imagen. Se puede pensar a una imagen como una clase y a los contenedores como una instancia de la misma.
3. DockerFIle -> Es un archivo de texto donde defines cómo se construye tu imagen.
4. Docker Engine -> Es el motor que ejecuta los contenedores, en el se gestiona el tema de la memoria, ram, etc.
5. Docker Hub -> Es un repositorio público donde puedes subir o descargar imágenes.

Ahora bien, el tema principal de esta práctica fue el mapeo de puertos. El cual se puede explicar de la siguiente manera.

Un contenedor se ejecuta de manera aislada, pero si existen varios mecanismos para comunicarnos con el contenedor. Uno de ellos es el mapeo de puertos. El parámetro -p nos permite mapear un puerto del host a un puerto del contenedor.

Ejemplo: 
docker run -d -p 8080:80 nginx

Aunque tambien se puede mapear varios puertos o incluso por rangos.

docker run -d -p 8080:80 -p 8081:81 nginx

## Aprendizajes en mi formación profesional 
Siento que todo este conocimiento de ambas prácticas realizadas es de gran ayuda para lo mas cercano que tengo ahora que son mis tareas academicas, con todo lo aprendido tengo una nueva manera de que probar los sistemas que desarrollemos funcionen perfectamente en cualquier computadora. Y seguramente ya en el futuro esta herramienta siga siendo igual de util, debido a que funciona perfectamente.

## Problemas en la práctica
No hubo grandes problemas al realizar la práctica, solo hubo pequeños inconvenientes con unos comando que tras leer su documentación se soluciono. A breves rasgos no se podia ejecutar el comando sin unos paraemtros necesarios.

## Docker Secrets
Cuando se crean contenedores, muchas veces se almacenan información sensible, como: 
- Contraseñas
- Tokens o claves API
- Certificados o llaves privadas
El problema esta que si colocas estas claves en el codigo fuente o en variables de entorno, cualquiera que vea la imagen podria obtener esta información. Es por ello que existe los Docker Secrets.

Docker secrets solo funciona cuando Docker está en modo Swarm. Esto convierte a tu máquina en el nodo principal.
docker swarm init 

Paso 1: Gestionar un secreto 
Supongamos que queremos guardar una contraseña de base de datos llamada 123456. Se crea de la siguiente manera:
echo "123456" | docker secret create db_password -

Usando el siguiente comnado podemos verificar que se creo
docker secret ls

Paso 2: Crear un servicio que use el secreto

docker service create \
  --name mysql_secure \
  --secret db_password \
  -e MYSQL_ROOT_PASSWORD_FILE="/run/secrets/db_password" \
  mysql:latest

Las ventajas de usar Docker Secrets son:
- Cifra automaticamente
- Acceso restringido: Solo los servicios seleccionados pueden leer el secreto
- Temporalidad: Los secretos no se escriben en disco dentro del contenedor, solo se montan mientras el contenedor vive.
- Sin exposición: No aparecen en variables de entorno, logs o Docker inspect.

  RICARDO VILLARREAL

