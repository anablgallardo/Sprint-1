# Ejercicio 3: Docker Compose Avanzado


## Descripción
En este ejercicio se ha creado un archivo docker-compose.yml que define varios servicios relacionados.

El objetivo es estructurar una aplicación multi-servicio que funcione de forma coordinada.

## Servicios

- **PHP + Apache**: Servidor web con PHP 8.1 con Apache
- **MySQL 8.0**: Base de datos
- **Nginx**: Servidor proxy inverso

## Configuración

### `.env`
Archivo con las variables de entorno sensibles utilizadas por el contenedor MySQL:

```env
MYSQL_ROOT_PASSWORD=rootpass
MYSQL_DATABASE=mydb
MYSQL_USER=myuser
MYSQL_PASSWORD=password
```