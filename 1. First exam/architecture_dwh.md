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
***
## Cualidades del DW
    * Maneja un gran volumen de datos
    * Almacena datos agregados, actuales e historicos
    * Estructura los datos de forma multidimensional
    * Tiene redundancia minima
***
## DHW vs DW
![image](https://i.postimg.cc/SscPzjdQ/Diferencia-entre-DHW-DW.jpg)
***
# Arquitectura del DWH
![image](https://user-images.githubusercontent.com/30439829/193495396-3e392cad-2829-487b-b985-72635fb5b154.png)</br>

## Introduccion
- Los datos se extraen de distintas fuentes (distintos formatos y arquitecturas).
- Los datos se integran, transforman y cargan en el DW.
- En el DW se contruyen cubos multidimensionales.
- Se accede al Cubo del DW con herramientas de consulta o analisis.
***
## 1. Data sources
Son datos transaccionales que genera una empresa a diario. Tambien pueden ser datos externos complementarios de multiples fuentes.<br>
![image](https://user-images.githubusercontent.com/30439829/193496221-ebafdfa3-38df-445f-a2e0-587ffca9d59c.png)</br>
***
## 2. Load Manager
Ejecuta y calendariza los procesos de integracion:
- Extrae datos de data sources.
- Manipula, integra y transforma los datos.
- Carga los resultados en el DW.
***
## Integracion de datos
    - Tecnicas y procesos para extraer, manipular, controlar, integrar, depurar, cargar y actualizar el DW. Desde la extraccion hasta la carga de datos en el DW.
***
### Proceso ETL
    - Extraccion.- Datos de diversas fuentes son extraidos y persistidos en almacenamiento(s) intermedio(s) (Staging Area) para poder:
        - Manipular datos sin sobrecargar el data sources
        - Crear una capa de abstraccion entre lectura y carga
        - Almacenar y gestionar metadatos generados
        - Facilitar la integracion

    - Transformacion.- Procesa los datos para hacerlos consistentes, compatibles y congruentes con el  DW.
        - Codificacion
        - Medida de Atributos
        - Fuentes multiples
        - Proceso de (Data Cleansing - Data Quality)
        - Algunos casos comunes:
- Codificacion <br>
![image](https://user-images.githubusercontent.com/30439829/193498031-d5353160-9e0b-4a5e-b4c7-ed753bdaa6bb.png)</br>
- Medida de Atributos<br>
![image](https://user-images.githubusercontent.com/30439829/193498195-691a1494-f3b4-4c12-8251-8353d5053e4b.png)</br>
- Fuentes multiples (elegir una) <br>
![image](https://user-images.githubusercontent.com/30439829/193498270-05f7c6c9-f0b1-442f-96b8-8467043ff6e8.png)</br>
## - Data Cleansing
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

## Carga.- Carga los datos y actualiza el DW.
    - Carga Inicial (Initial Load):
            Primera carga al DW, gran cantidad de registros que toman un tiempo considerable.

## - Actualizacion periodica (Update).
Insercion de pequeños volumenes de datos. Solo agrega al DW datos de la ultima actualizacion **(Delta de cambios)**.
| Acciones para identicar Delta de cambios |
| --- |
| - Cotejar instancias de Data Sources. |
| - Utilizar Triggers para informar cambios de Data Sources. |
| - Recurrir a Time Stamps. |
| - Comparar datos existentes entre Data Source y DW. |
| - Tecnicas mixtas |

## Carga Total (Full Load)
Se da cuando este control requiere demasiado esfuerzo. Permite cargar el DW desde cero. El DW se debe vaciar previamente.<br>
| Incluye los siguientes conceptos |
| --- |
| Relaciones muchos a muchos|
| Claves subrogradas|
| Dimensiones lentamente cambiantes|
| Dimensiones degeneradas|

![image](https://i.postimg.cc/65vSgG0Y/Proceso-Load.jpg)
# 3. Data Warehouse Manager
- Esta compuesto por:
    - El DW (SGBD)
    - Conexiones a base de datos y otros data sources
    - Las estrcuturas de datos (Cubos multidimensionales, Business Models, etc)
    - Informacion de autenticacio y autorizacion
    - Otros metadatos
***
- Base de datos multidimensional
    - Compuesto por:
        - Tablas de hechos
        - Tablas de dimensiones
***
- Tipos de Modelos logicos
    - Existen tres formas de modelar las tablas de hechos y dimensiones.
        - Esquema en estrella (Star Scheme)<br>
        ![image](https://i.postimg.cc/wjGHK4bL/Esquema-estrella.jpg)<br>
        - Esquema copo de nieve (Snowflake Scheme)<br>
        ![image](https://i.postimg.cc/d0ZFJRzX/Esquema-copo-de-nieve.jpg)<br>
        - Esquema constelacion (Starflake Scheme)<br>
        ![image](https://i.postimg.cc/ydqHxgKN/Esquema-constelacion.jpg) <br>
    - Se diferencia por:
        - Estrella tiene un centro y no tiene ramificacion en los extremos
        - Copo de nieve tiene un centro y tiene ramificacion en los extremos
        - Constelacion es la union de mas estrellas.
    - Estos modelos facilitan el acceso a consultas complejas
    - Estan desnormalizadas o semi desnormalizadas reduciendo los joins.
***
- Tipos de implementacion
    - Relacional - ROLAP
        - Los cubos se generan en el momento en que se realizan las consultas. El proceso se describe en:
            - Metadata del cubo: Indicadores, atributos, jerarquias, etc.
            - Almacenar metadata.
            - Realizar el mapeo del visor OLAP.
            - ROLAP hace uso exahustivo del cache evitando consultar dos veces el mismo dato.
    - Multidimensional - MOLAP
        - Precalcula los cubos multidimensionales y los almacena fisicamente. El proceso se describe en:
            - Seleccionar indicadores, atributos, jerarquias, etc.
            - Precalcular datos del cubo. Todas las combinaciones posibles de jerarquias de cada dimension.
            - Precalcular y guardar el cubo cada que se actualiza el DW.
    - Hibrido - HOLAP
        - Combina las anteriores dos implementaciones.
            - ROLAP para navegar y explorar a bajo nivel de granularidad.
            - MOLAP para explotacion de datos precalculados.
***
- Tablas de dimensiones
    - Contiene datos cualitativos
    - Represetan aspectos de interes
    - Pueden filtrar y manipular hechos almacenados.
    - Contiene:
        - Clave principal
        - Claves foraneas
        - Datos de referencia primarios
        - Datos de referencia secundarios

    - Tiempo
        - Toda la informacion posee un sello de tiempo que determina la ocurrencia del hecho especifico, representando versiones de una misma situacion.
    - Fecha y hora
        - Se confecciona dos tablas.
            - Una en fechas
            - Una en horas
***
- Tablas de hechos
    - Contienen datos cuantitativos
    - Filtrados, agrupados y explorados a traves de condiciones definidas en tablas de dimensiones.
    - Hechos vs Indicadores
        - Los hechos son aquellos que residen en una tabla
        - Los indicadores hacen uso de los hechos para obtener un valor analizable
            - Se hacen agregaciones sobre el mismo.
    - Hechos basicos
        - Son aquellos que se encuentran representados por un campo de una tabla.
    - Hechos derivados
        - Son aquellos que se obtienen a partir de una expresion, combinando algunos hechos con operaciones matematicas.
    - Agregadas
        - Se genera luego de hacer la consulta a la tabla de hechos. (Respuesta para analisis)
    - Preagregadas
        - Se genera antes de la consulta a la tabla de hechos. (Al momento de poblar DW)
***
- OLTP vs DW OLAP
    - OLTP (DB Transaccional)
        - Orientado al procesamiento
        - Matricial
        - Normalizado
        - Instancia de objeto
    - OLAP (DB Analitica)
        - Orientado al negocio (consulta y analisis)
        - Multidimensional
        - desnormalizado
# 4. Query Manager 
- Encargado de realizar operaciones necesarias para soportar los procesos de gestion y ejecucion:
    - Slice & dice
        - Dar vuelta al cubo y rebanar encontrado el dato que me interesa.
    - Consultas relacionales
    - Consultas propias de analisis de datos.
    - Drill - Down
        - Implica ir de lo general a lo especifico.
    - Drill - Up
        - Implica ir de lo especifico a lo general.
    - Drill - Across
        - Implica agregar un atributo a la consulta como nuevo criterio de analisis.
    - Roll - Across
        - Implica eliminar el criterio de analisis.
    - Pivot
        - Permite seleccionar el order de visualizacion de los atributos e indicadores.
    - Page
        - Presenta el cubo dividido en secciones, a traves de valores de atributo.
    - Drill - Through
        - Permite visualizar cuales son los datos relacionados al valor de un indicador.
    
# 5. Software Analytics
- Nos referimos a todas aquellas herramientas de software mediantes las cuales podremos explorar y explotar los datos. <br>
- Interaccion <br>
    ![image](https://i.postimg.cc/wTDJ74rp/Interaccion.jpg) <br>
    - caracteristicas
        - Accesibilidad
        - Apoyo en la toma de decisiones
        - Orientacion a los usuarios finales
            - Reporting
            - OLAP
            - Dashboards
            - Data mining

# 6. Users
| acciones |Users OLTP | Users DW|
| --- | --- | --- |
| acceso concurrente| - muchos| - pocos|
| tipo de consultas|- predefinidos| - complejos, no predecibles y no anticipadas|
| registros consultados|- pocos| - muchos|
| tiempo de respuesta|- critico| - no critico|
| acciones permitidas|- Crud| - Consulta|
***
# Implementacion de un DW
## 7. Arquitectura de 2 niveles
![image](https://i.postimg.cc/Dfdtrjhn/Arquitectura-de-dos-niveles.jpg)
## 8. Arquitectura de 3 niveles
![image](https://i.postimg.cc/ZKbXV8Y3/Arquitectura-de-tres-niveles.jpg)
## 9. Arquitectura ascendente
![image](https://i.postimg.cc/3NBV3R1d/Arquitectura-ascendente.jpg)