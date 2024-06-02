## Esquema para el ejercicio
![Imagen](imagenes/esnquema-ejercicio5.PNG)

### Crear la red
# COMPLETAR

docker network create net-wp

### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
# COMPLETAR
docker run -P -d --name mysql --env-file="C:\Users\Personal\Downloads\contrasena.txt" --network net-wp mysql:8
### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# COMPLETAR
docker run -d --name wordpress -p 8080:80 --network net-wp wordpress

De acuerdo con el trabajo realizado, en la el esquema de ejercicio el puerto a es **8080**

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/8eb09c73-59af-49e3-9c76-ca08e9a06259)


![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/8509792b-4e3b-41c8-a7eb-d1ba8322909c)



# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/03b51fe3-052d-47d1-97d2-80c44c1179e0)
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/a304e196-6c9c-4f0e-86b6-c8173b2740c2)

Desde el panel de admin: cambiar el tema y crear una nueva publicación.
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/07af2715-4455-4015-87f4-22f8f7fd867c)

creación de  la nueva Publicación 

![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/36ce6180-0826-4bad-8fcc-1b6a0d09061f)


Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/760a7139-15ad-439c-81e9-929af85327bd)


### Eliminar el contenedor wordpress
docker rm wordpress
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/67463e10-a0a3-48dc-9ded-d8dc2642523d)


### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

docker run -d --name wordpress -p 9300:80 wordpress

### ¿Qué ha sucedido, qué puede observar?
nos redirige al inicio donde tenemos que configurar nuevamente wordpress
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/b8910c49-c04e-4052-aaeb-077a1e4a06ca)







