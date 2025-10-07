# Variables de Entorno
### ¿Qué son las variables de entorno?

Las variables de entorno son valores dinámicos con nombre que viven fuera del código de un programa, pero que un proceso puede consultar para influir en su comportamiento. Almacenan información como rutas de directorios, configuraciones o claves secretas, permitiendo adaptar el entorno de ejecución de un programa sin modificar su código base. 

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.
```
C:\Users\P3E010-D>docker run -d --name contenedor777 -e username=user123 -e role=admin nginx:alpine
```
<img width="1121" height="74" alt="image" src="https://github.com/user-attachments/assets/17c700ea-9330-43a6-949e-9fdb377147e6" />

<img width="969" height="757" alt="image" src="https://github.com/user-attachments/assets/6b01e1b0-6a50-46de-8392-aabb9e780735" />



### Crear un contenedor con la imagen de mysql, mapear todos los puertos
# COMPLETAR

### ¿El contenedor se está ejecutando?
# COMPLETAR

### Identificar el problema
# COMPLETAR

### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### Crear un contenedor con mysql, mapear todos los puertos y configurar las variables de entorno mediante un archivo
# COMPLETAR

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR 

### ¿Qué bases de datos existen en el contenedor creado?
# COMPLETAR
