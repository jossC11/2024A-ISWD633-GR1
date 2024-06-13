# VOLUMEN TIPO HOST
Un volumen host (o bind mount) es un tipo de volumen donde se monta un directorio o archivo específico del sistema de archivos del host en un contenedor.

```
docker run -d --name <nombre contenedor> -v <ruta carpeta host>:<ruta carpeta contenedor> <imagen> 
```

### Crear un volumen tipo host con la imagen nginx:alpine, para la ruta carpeta host: directorio en donde se encuentra la carpeta html en tu computador y para la ruta carpeta contenedor: /usr/share/nginx/html esta ruta se obtiene al revisar la se obtiene desde la documentación
![Volúmenes](imagenes/volumen-host.PNG)
# COMPLETAR CON EL COMANDO
```
docker run -d --name contenedorVolumen -p 8080:80 -v "C:/Users/Personal/OneDrive - Escuela Politécnica Nacional/Escritorio/Practica3:/usr/share/nginx/html" nginx:alpine
```
### ¿Qué sucede al ingresar al servidor de nginx?
```
Sale que existe  un error 403
```
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/f47ac0de-b331-4f40-841e-b5d77251171a)


### ¿Qué pasa con el archivo index.html del contenedor?
```
No existe en archvo index.html en el contenedor
```
### Ir a https://html5up.net/ y descargar un template gratuito, descomprirlo dentro de nginx/html
### ¿Qué sucede al ingresar al servidor de nginx?
```
 Ahora si se visualiza  la pagina que nos descargammos 
```
 ![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/085e10cb-ec43-4d3f-a940-c158a239ebff)


### Eliminar el contenedor
```
docker rm -f contenedorVolumen   
```
### ¿Qué sucede al crear nuevamente el mismo contenedor con volumen de tipo host a los directorios definidos anteriormente?
```
la misma página segue siendo visible al recrear el contenedor debido a la persistencia de los datos en el host.
```
### ¿Qué hace el comando pwd?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA
```
El comando nos muestra la ruta del directorio actual en el que estamos trabajando .
```

### Volumen tipo host usando PWD y PowerShell
```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v ${PWD}/<ruta relativa>:<ruta absoluta> <nombre imagen>:<tag> 
```

### Volumen tipo host usando PWD (Git Bash)

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v $(pwd -W)/html:/usr/share/nginx/html <nombre imagen>:<tag> 
```

### Volumen tipo host usando PWD (en Linux)

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v $(pwd)/html:/usr/share/nginx/html <nombre imagen>:<tag> 
```

