# Iceberg - Trino - Iceberg-Rest Setup

Este proyecto configura un entorno de análisis de datos utilizando Apache Iceberg, Trino, y un servidor REST de Iceberg, orquestado con Docker Compose. Este setup es ideal para trabajar localmente, y aprender sobre la arquitectura moderna de data lakehouses, soportando almacenamiento en AWS S3.

>[!WARNING]  
> ¡No uses este setup en producción!

## Servicios

1. **Spark Notebook Server** (`spark-iceberg`): Proporciona un entorno de Apache Spark con Jupyter Notebook para interactuar con datos.
2. **Trino Server** (`trino`): Motor de consultas distribuido que permite realizar análisis de datos en varias fuentes.
3. **Iceberg REST Server** (`catalog`): Ofrece una interfaz REST para gestionar catálogos de datos con Apache Iceberg.
4. **S3 Storage** (`storage`): Emula un almacenamiento compatible con S3 para el manejo de datos.

## Pre-requisitos

- Docker
- Docker Compose

## Variables de Entorno Comunes

Estas variables de entorno son compartidas por los servicios:
- `AWS_ACCESS_KEY_ID`: Clave de acceso para AWS (valor predeterminado: `admin`)
- `AWS_SECRET_ACCESS_KEY`: Clave secreta de AWS (valor predeterminado: `password`)
- `AWS_REGION`: Región de AWS configurada como `us-east-1`

## Configuración de Red

Los servicios comparten la red definida como `iceberg_net`.

## Uso

1. Clonar el repositorio en tu máquina local.
2. Asegúrate de tener Docker y Docker Compose instalados.
3. Ejecuta el comando:

    ```bash
    docker-compose up -d
    ```

   Esto iniciará todos los contenedores en segundo plano.

4. Puedes acceder a los servicios en los siguientes puertos:
   - **Spark Notebook**: `http://localhost:8888`
   - **Trino**: `http://localhost:9047`
   - **Minio**: `http://localhost:9001`

## Notas

- Asegúrate de modificar los valores de `AWS_ACCESS_KEY_ID` y `AWS_SECRET_ACCESS_KEY` si deseas conectarte a un servicio de almacenamiento S3 real.
- Revisa y ajusta los puertos en el archivo `docker-compose.yaml` si tienes conflictos de red.

## Parar el Entorno

Para detener todos los contenedores, utiliza el comando:

```bash
docker-compose down
```

## Contribución
Si quieres mejorar o ajustar este setup enviar tus contribuciones mediante pull requests.


