# Variables de Entorno
### ¿Qué son las variables de entorno
# COMPLETAR

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.
```
docker run -d --name MinuevoContenedor nginx:alpine  -e username -e role=admin
```
# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/1aa34cff-270f-4f8d-b789-25d468e295b5)


### Crear un contenedor con mysql:8 , mapear todos los puertos
```
docker run -P -d --name mysqlDocker mysql:8
```
### ¿El contenedor se está ejecutando?
```
En contenedor No se esta ejecutando , esto lo podemos comprobar en docker o ejecutando  el comando docker ps -a 

```
### Identificar el problema
```
El problema es que el contenedor de MySQL requiere una configuración específica para la contraseña del usuario root. 
```
### Eliminar el contenedor creado con mysql:8 
```
docker rm mysqlDocker
```
### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

Previo a esto es necesario crear el archivo y colocar las variables en un archivo, **.env** se ha convertido en una convención estándar, pero también es posible usar cualquier extensión como **.txt**.
```
docker run -d --name <nombre contenedor> --env-file=<nombreArchivo>.<extensión> <nombre imagen>
```
**Considerar**
Es necesario especificar la ruta absoluta del archivo si este se encuentra en una ubicación diferente a la que estás ejecutando el comando docker run.

### Crear un contenedor con mysql:8 , mapear todos los puertos y configurar las variables de entorno mediante un archivo
```
docker run -P -d --name mysqlDocker2 --env-file=C:\Users\Personal\Downloads\contrasena.txt mysql:8
```
# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR 
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/dd99b04f-3e48-4562-ada2-6836861691e4)
# ¿Qué bases de datos existen en el contenedor creado?

mediante docker exec -it mysqlDocker2 mysql -u root -p   

![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/5c3c2ffc-0460-4a35-9a47-a5ebe2c1e29d)

y posteriormente show databases;  , podemos visualizar las DB existentes 

![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/09c9c44b-2bba-4628-9b62-b10a3967c4a5)



### ¿Qué bases de datos existen en el contenedor creado?
# COMPLETAR
![Uploading image.png…]()
