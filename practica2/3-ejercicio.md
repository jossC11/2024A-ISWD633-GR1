### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:11.21-alpine3.17
docker run -d --name postgresContainer postgres:11.21-alpine3.17


### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4

docker run -d --name pgadmin4 -p 80:80 -e PGADMIN_DEFAULT_EMAIL=joselyn.plco@epn.edu.ec -e PGADMIN_DEFAULT_PASSWORD=administrador dpage/pgadmin4

La figura presenta el esquema creado en donde los puertos son:
- a: 8080
- b: 80
- c: 5032

![Imagen](imagenes/esquema-ejercicio3.PNG)

## Desde el cliente
### Acceder desde el cliente al servidor postgres creado.
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/39c2aff7-388c-4cf7-9038-1bbbda923d25)


### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/18f1ac9a-0da6-4b81-8c19-d3f9324c8192)

Para la creación de tablas  
![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/4026ba18-ae63-4472-a63b-6c1d5d211f20)

![image](https://github.com/jossC11/2024A-ISWD633-GR1/assets/94476123/91e0e7d3-22dd-4807-bc56-f7adf150af70)

## Desde el servidor postgresl
### Acceder al servidor

### Conectarse a la base de datos info
# COMPLETAR
### Realizar un select *from personas
# AGREGAR UNA CAPTURA DE PANTALLA DEL RESULTADO
