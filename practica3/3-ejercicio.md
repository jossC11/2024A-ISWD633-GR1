## Esquema para el ejercicio
![Imagen](imagenes/esquema-ejercicio3.PNG)

### Crear red net-wp

docker network rm net-wp


### Para que persista la información es necesario conocer en dónde mysql almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/)
En el esquema del ejercicio la carpeta contenedor (a) es C:/Users/Personal/OneDrive - Escuela Politécnica Nacional/Escritorio/Practica3/ejercicio3
Ruta carpeta host: .../ejercicio3/db

### ¿Qué contiene la carpeta db del host?
db esta vacia en un inicio  

### Crear un contenedor con la imagen mysql:8  en la red net-wp, configurar las variables de entorno: MYSQL_ROOT_PASSWORD, MYSQL_DATABASE, MYSQL_USER y MYSQL_PASSWORD

docker run -d --name contMysql --network net-wp ^
  -v "C:\Users\Personal\OneDrive - Escuela Politécnica Nacional\Escritorio\Practica3\ejercicio3\db:/var/lib/mysql" ^
  -e MYSQL_ROOT_PASSWORD=rootpassword ^
  -e MYSQL_DATABASE=wordpress ^
  -e MYSQL_PASSWORD=Bookoflove11 ^
  mysql:8


### ¿Qué observa en la carpeta db que se encontraba inicialmente vacía?
Ahora se encuentran  varios archivos de configuración de Mysql entre  otros archivos  

### Para que persista la información es necesario conocer en dónde wordpress almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/)
En el esquema del ejercicio la carpeta contenedor (b) es  /var/www/html.
Ruta carpeta host: .../ejercicio3/www

### Crear un contenedor con la imagen wordpress en la red net-wp, configurar las variables de entorno WORDPRESS_DB_HOST, WORDPRESS_DB_USER, WORDPRESS_DB_PASSWORD y WORDPRESS_DB_NAME (los valores de estas variables corresponden a los del contenedor creado previamente)
docker run -d --name wordpressJP --network net-wp -p 9500:80 -v "C:\Users\Personal\OneDrive - Escuela Politécnica Nacional\Escritorio\Practica3\ejercicio3\www":/var/www/html -e WORDPRESS_DB_HOST=contMysql:3306 -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=Bookoflove11 -e WORDPRESS_DB_NAME=wordpress wordpress
### Personalizar la apariencia de wordpress y agregar una entrada
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/a720616c-ff7d-4779-afcb-93a1bda91fbe)

![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/fd145bf8-6619-40ec-856e-39909f6e6051)


### Eliminar el contenedor y crearlo nuevamente, ¿qué ha sucedido?
Al crear nuevamente el contenedor y abrir el puerto se  observa  la entrada creada anteriormente  lo que quiere decir que las configuraciones que se hicieron se han guardado .

![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/feec1ba8-4670-48a8-a778-408276d4de78)




