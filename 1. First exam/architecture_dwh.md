# Arquitectura del DWH
![image](https://user-images.githubusercontent.com/30439829/193495396-3e392cad-2829-487b-b985-72635fb5b154.png)</br>

## Introduccion
- Los datos se extraen de distintas fuentes (distintos formatos y arquitecturas).
- Los datos se integran, transforman y cargan en el DW.
- En el DW se contruyen cubos multidimensionales.
- Se accede al Cubo del DW con herramientas de consulta o analisis.

## 1. Data sources
Son datos transaccionales que genera una empresa a diario. Tambien pueden ser datos externos complementarios de multiples fuentes.
![image](https://user-images.githubusercontent.com/30439829/193496221-ebafdfa3-38df-445f-a2e0-587ffca9d59c.png)</br>

## 2. Load Manager
Ejecuta y calendariza los procesos de integracion:
- Extrae datos de data sources.
- Manipula, integra y transforma los datos.
- Carga los resultados en el DW.
### Integracion de datos
Tecnicas y procesos para extraer, manipular, controlar, integrar, depurar, cargar y actualizar el DW. Desde la extraccion hasta la carga de datos en el DW.

### Proceso ETL:
### Extraccion 
Datos de diversas fuentes son extraidos y persistidos en almacenamiento(s) intermedio(s) (Staging Area) para poder:
- Manipular datos sin sobrecargar los data sources.
- Crear una capa de abstraccion entre lectura y carga.
- Almacenar y gestionar metadatos generados.
- Facilitar la integracion.

### Transformacion
Procesa los datos para hacerlos consistentes, compatibles y congruentes con el DW.</br>
Algunos casos comunes:
#### - Codificacion
![image](https://user-images.githubusercontent.com/30439829/193498031-d5353160-9e0b-4a5e-b4c7-ed753bdaa6bb.png)</br>
#### - Medida de Atributos
![image](https://user-images.githubusercontent.com/30439829/193498195-691a1494-f3b4-4c12-8251-8353d5053e4b.png)</br>
#### - Fuentes multiples (elegir una)
![image](https://user-images.githubusercontent.com/30439829/193498270-05f7c6c9-f0b1-442f-96b8-8467043ff6e8.png)</br>
Procesos que realiza:
#### - Data Cleansing
Elimina datos erroneos o irrelevantes y arregla inconsistencias.</br>
Acciones contra:
|  Outliers (Datos anomalos) | Missing Values (Datos faltantes) |
| --- | --- |
| - Ignorarlos | - Ignorarlos |
| - Eliminar columna | - Eliminar columna |
| - Filtrar columna | - Filtrar columna |
| - Filtrar fila erronea | - Filtrar fila erronea |
| - Reemplazar valor | - Reemplazar valor |
| - Discretizar valores de las columnas | - Esperar a que esten disponibles |

### Carga
Ejecuta tareas relacionadas con: 
#### - Carga Inicial (Initial Load)
Primera carga al DW, gran cantidad de registros que toman un tiempo considerable.
#### - Actualizacion periodica (Update).
Insercion de perqueños volumenes de datos. Solo agrega al DW datos de la ultima actualizacion **(Delta de cambios)**.
| Acciones para identicar Delta de cambios |
| --- |
| - Cotejar instancias de Data Sources. |
| - Utilizar Triggers para informar cambios de Data Sources. |
| - Recurrir a Time Stamps. |
| - Comparar datos existentes entre Data Source y DW. |
| - Tecnicas mixtas |
#### Carga Total (Full Load)
Se da cuando este control requiere demasiado esfuerzo. Permite cargar el DW desde cero. El DW se debe vaciar previamente.

### 3. Data Warehouse Manager

### 4. Query Manager 

### 5. Software Analytics

### 6. Users
