# Ejercicio 4: Configurar un contenedor para servir una aplicación PHP + Nginx


## Descripción
En este ejercicio se ha creado un archivo `docker-compose.yml` que define varios servicios relacionados.

El objetivo es crear una aplicación web con PHP utilizando Nginx como servidor web.

## Estructura
Nuestro ejercicio va a tener la siguiente estructura de archivos y carpetas:

├── Ejercicio-4
│   ├── docker-compose.yml
│   ├── README.md
│   └── www       
│       └── index.php
│   └── nginx       
└──     └── default.conf

## Servicios

- **Nginx**: Servidor proxy inverso
- **PHP-FPM**: Servidor web con PHP-FPM 8.1 

## Configuración

### `default.conf`
Archivo de configuración de Nginx para que funcione con PHP-FPM:

```default.conf
server {
    listen 80;
    server_name localhost;
    root /var/www/html;
    index index.php index.html;

    location / {
        try_files $uri $uri/ =404;
    }

    location ~ \.php$ {
        include fastcgi_params;
        fastcgi_pass php:9000;
        fastcgi_param SCRIPT_FILENAME /var/www/html$fastcgi_script_name;
    }
}
```

### `index.php`
Archivo de prueba para verificar que Nginx y PHP-FPM están funcionando de manera correcta:

```index.php
<?php
phpinfo();
?>
```