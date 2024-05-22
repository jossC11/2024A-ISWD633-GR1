# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](imagenes/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 
la relación es que la imagen es la plantilla a partir de la cual se crea un contenedor en Docker entonces podemos entender que una imagen puede ser referenciada y utilizada por múltiples contenedores, permitiendo así su reutilización y acceso compartido.


![Imagen y contenedores](imagenes/imagenYcontenedores.JPG)
## Comandos para imágenes

### Descargar imagen
docker pull hello-world

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
```
docker pull hello-world
```
**¿Qué es nginx**
```
Nginx es un servidor web ligero de código abierto que también puede funcionar como proxy inverso, balanceador de carga y servidor de correo electrónico.
```
Descargar la imagen  **nginx** en la versión **alpine**
```
docker pull nginx:alpine
```
### Listar imágenes
```
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/d02f9be0-6c0b-4d4f-be87-21627de47716)

```
**Identificadores**
En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
```
docker inspect hello-world
```
**¿Con qué algoritmo se está generando el ID de la imagen**
```
el  ID se esta generando con sha256
```
### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world :
```
docker rmi hello-world:latest
```
-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

