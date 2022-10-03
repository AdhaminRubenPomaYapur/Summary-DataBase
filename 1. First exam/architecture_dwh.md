# Data WareHousing
* Es el proceso que reune y ordena las tareas inherentes a:
    * Extraccion, Transformacion, consolidacion integracion y centralizacion de datos internos y externos.
    * Permite el acceso, analisis y exploracion.
    * Da soporte a la toma de decisiones estrategico y tactico.
# Data Warehouse
* Es una base de datos que posee una estructura multidimensional.
* Es una coleccion de datos orientada al negocio, integrada, variante en el tiempo y no volatil para el soporte de toma de decisiones.
![image](https://i.postimg.cc/PqN74TbZ/Data-Ware-House.jpg)

* Orientado al negocio
    * Solo se ingresan datos relevantes.
    * Se manejan entidades de alto nivel.
    * La estructura es multidimensional.
        * Hechos
            * Son campos claves que se unen a las tablas de dimension.
            * Son cuantitativas.
        * Dimension
            * Son tablas desnormalizadas.
            * Son cualitativos: jerarquicos o de clasificacion
            * Ofrecen informacion caracteristicas de las tablas de hechos.
***
* Integrada
    * Implica que los datos de origenes heterogeneos deben ser analizados para asegurar su calidad y limpieza. El proceso que hace esto de denomina Integracion de datos, La tecnica mas utilizadas es el de:
        * ETL (Extraction, Transformation and Load)
        * Origene de datos mas comunes:
            * Producidas por tipos de usuario
            * Producidas por areas o departamentos de la org.
            * Producidas por diferentes data sources.
***
* Variante en el tiempo
    * En el DW los datos son almacenados junto a datos historicos y cada dato es marcado con su sello de tiempo. (timestamps)
    * Mediante ese sello se puede viajar a diferentes versiones de una misma situacion.
***
* No volatil
    * La informacion solamente sera util para el analisis siempre y cuando sea estable.
    * Es decir que no cambian hasta la siguiente subida de datos.
![image](https://i.postimg.cc/tCRfjkbR/No-volatil.jpg)

* Cualidades del DW
    * Maneja un gran volumen de datos
    * Almacena datos agregados, actuales e historicos
    * Estructura los datos de forma multidimensional
    * Tiene redundancia minima
***
# DHW vs DW
![image](https://i.postimg.cc/SscPzjdQ/Diferencia-entre-DHW-DW.jpg)
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
