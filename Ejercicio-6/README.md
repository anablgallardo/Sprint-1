# Ejercicio 6: Monitorización Básica con Prometheus

## Descripción
En este ejercicio se ha creado un archivo `docker-compose.yml` que define varios servicios relacionados.

El objetivo es configurar Prometheus para recolectar métricas de tus servicios en contenedores.

## Servicios

- **Prometheus**: Herramienta de monitorización
- **cAdvisor**: Herramienta que se utiliza para monitorear el uso de recursos y las características de rendimiento de contenedores en ejecución.

## Configuración

### `prometheus.yml`
Archivo de configuración para que Prometheus monitorice a cAdvisor y a sí mismo:

```prometheus.yml
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: 'prometheus'
    static_configs:
    - targets: 
       - 'prometheus:9090'

  - job_name: 'cadvisor'
    static_configs:
    - targets: 
       - 'cadvisor:8080'
```