# Ejercicio 7: Instalación de Grafana

## Descripción
En este ejercicio se ha creado un archivo `docker-compose.yml` que define varios servicios relacionados.

El objetivo es configurar Grafana para construir una vista visual del rendimiento de tu entorno en tiempo real.

## Servicios

- **Promtheus**: Herramienta de monitorización
- **cAdvisor**: Herramienta que se utiliza para monitorear el uso de recursos y las características de rendimiento de contenedores en ejecución.
- **Grafana**: Plataforma que se utiliza para la visualización de datos, análisis y monitoreo de insfrestructuras de TI.

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