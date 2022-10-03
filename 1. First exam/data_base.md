# Summary

# 1. database
    1. Data base.- Es una coleccion de datos persistentes que pueden compartirse e interrelacionarse.
***
        1. Persistente.- Significa que los datos residen en un almacenamiento estable se pueden eliminar o archivar.
***
        2. Compartir.- Significa que una base de datos puede tener multiples usos y usuarios proporciona una memoria comun para varias funciones.
***
        3. Interrelacion.- Significa que los datos almacenados como unidades separadas se pueden conectar para mostrar un cuadro completo.


# 2. Entity Relationship (ER)
    1. Entidad.- Es un conjunto de datos generalmente sobre un tema, al que puede accederse de forma conjunta. En si representa un objeto de la vida real.

        1. Entidad debil.- Depende su existencia de otra entidad asociada a la misma.
***
    2. Relacion.- Es la asignacion de una regla por el cual se relaciona una entidad con  otra. Indicando su cardinalidad.
***
    3. Cardinalidad.- Define la relacion en un contexto numerico, entre las entidades.

        1. Uno a uno        (1-1)
        2. Uno a muchos     (1-N)
        3. muchos a muchos  (N-M)
        4. Cardinalidad obligatoria
        5. Cardinalidad opcional
***
# 3. (DBMS) Data base Management System
    * Es un conjunto de componentes que soportan la creacion, el uso y el mantenimiento de base de datos inicialmente. Proporcionan almacenamiento y recuperacion de datos.
    
***
    1. Tabla.- Se denomina a un arreglo de datos en dos dimensiones. Las columnas son los atributos de la entidad y las filas son los datos del objeto.

# 4. Data models
    1. Modelo conceptual.- Identifica las entidades y las diferentes relaciones entre estas.

        1. Incluye las entidades importantes y las relaciones entre ellas.
        2. No se especifican atributos ni cardinalidad.
        3. No se especifica nignuna clave principal.

    2. Modelo logico.- Describe los datos con el mayor detalle posible, independientemente de como se implementaran fisicamente en la base de datos.

        1. Incluye todas las entidades y relaciones entre ellos.
        2. Todos los atributos para cada entidad estan especificados.
        3. La clave principal para cada entidad esta especifica.
        4. Se especifican las claves externas (de la relacion entre diferentes entidades)
        5. Normalizacion de la base de datos.

    3. Modelo fisico.- Representa como se construira el modelo en la base de datos. Este modelo muestras todas las estructuras de tabla.

        1. Especificacion de todas las tablas y columnas.
        2. Las claves externas se usan para identificar relaciones entre tablas.
        3. La desnormalizacion puede ocurrir segun los requisitos del usuario.
***
# 5. Todo los requisitos que debe tener un modelo entidad relacion
    1. Entidad
    2. Relacion
        * Cardinalidad
            1. Claves primarias
                * Es un atributo que identifica de forma exclusiva cada registro en una            
                determinada tabla por entidad.
                    1. Reglas:
                        * Unica
                        * Inalterable
                        * Nunca nulo
            2. Claves foraneas
                * Es una clave foranea en un lugar foraneo, pueden no ser unicas.
            3. Claves primarias compuestas
                * Usa dos claves foraneas y se las suma entre si.
                * Usa la menor cantidad posible de atributos y que no tiendan a cambiar.
***
# 6. Roles para trabajar con base de datos
    1. Arquitecto:
        * Se encarga de construir la base de datos, estableciendo estandares para las 
            operaciones, programacion y seguridad de las bases de datos. Para garantizar
            que se desempeñen como se pretende.
        
        1. Datos maestros:
            * Son los datos centrales absolutamente esenciales para ejecutar operaciones.
***
    2. Desarrollador - Diseñador:
        1. DDL (Lenguaje de definicion de datos):
            * Es un lenguaje de programacion para definir estrucuturas de datos proporcionado 
                por los gestores de base de datos. Ofrece tres sentencias:
                    1. CREATE
                        * Crear base de datos, tablas, vistas, procedure, etc.
                    2. ALTER
                        * Modificar la estructura, añadir o borrar columnas de una tabla.
                    3. DROP
                        * Elimina objetos de la estructura o la base de datos.

        2. DML (Lenguaje de Manipulacion de datos):
            * Permite a los usuarios introducir datos para posteriormente realizar tareas de
                consultas o modificacion de los datos. Ofrece 4 formas de manipulacion de datos:
                    1. Select
                        * Realizar consultas
                    2. Insert
                        * Insertar valores
                    3. Update
                        * Modificar datos
                    4. Delete
                        * Eliminar datos
        3. DRL/DSL (Lenguaje de recuperacion de datos / Lenguaje de seleccion de datos)
            * Ofrece los comandos para recuperar datos del servidor, manipula los datos como 
                objetivo, en si ofrece todo lo anterior de un select. Ofrece 6 clausulas dentro 
                del contexto select:
                1. FROM
                    * Seleccion de un nombre de tabla en la base de datos.
                2. WHERE
                    * Especifica que filas va a traer.
                3. GROUP BY
                    * Ordena los datos en grupo
                4. HAVING
                    * Selecciona entre los grupos por Group BY
                5. ORDER BY
                    * Especifica un orden en los datos
                6. AS
                    * Provee un alias temporal para renombrar una columna de la tabla
***
    3. Administrador de base de datos:
        * Se encarga de los datos vivan una vida tranquila, help check diario, almacenamiento de registro y cuantas transacciones se hicieron.
***
# 7. Modelo de tres capas
    1. Capa de presentacion
        * Es la que ve el usuario, presenta el sistema al usuario, comunica la informacion y   
            captura la informacion del usuario en un minimo proceso

    2. Capa de logica de negocios
        * Es donde residen los programas que se ejecutan, reciben las peticiones del usuario
            y se envian las respuestas tras el proceso.

    3. Capa de datos
        * Es donde residen los datos, encargada de acceder a los mismos y responder solicitudes
            de almacenamiento o recuperacion de informacion desde la capa de negocio.
***
# 8. MDF (Main data file)
    * Es el archivo de base de datos principal .mdf que contiene los datos, asi como un esquema.
***
# 9. LDF (Load data file)
    * Es un archivo de base de datos que almacena todos los registros de transacciones / eventos
        que se ejecutan en la base de datos.
***
# 10. Detach
    * Desvincula el archivo del servidor de base de datos para poder mover y copiarlo.
        Sirve en caso se llene el disco duro o cambio de disco.
***
# 11. Modelo de implementacion de una base de datos
    1. Monolitico - Multiusuario (mainframe)
        * Una aplicacion desde un mismo lugar sostiene programas y bases de datos.

        1. Arreglo de discos: 
            * Es un conjunto de discos que se agrupan para lograr objetivos de redundancia
                o mejorar el rendimientos en los procesos de lectura y escritura, en los 
                volumenes de almacenamiento.

    2. Anillo Optico
        * Se conectaban diferentes computadoras a traves de un mismo cable.

    3. Cableado UTP
        * En red tenia error cuando dos usuarios manipulaban un mismo registro a la vez.
        * Ansi SQL resuelve este error poniendo bloqueos y tiempos de procesamiento.

    4. Cliente servidor
        * El servidor proporciona la informacion y el cliente es el que solicita esa informacion
            desde otra computadoras.

    5. Computacion distribuida
        * Son redes de computadoras que tienen alta disponibilidad, alta cohexion y bajo 
            acomplamiento por si alguna maquina deja de funcionar, esta no afecte a los demas.

    6. Servidores conectados a la nube
        * Esto es la integracion de nuestro servidores a una red mas grande con el fin de
            optimizar tiempos de respuesta y distribucion de carga.
***
# 12. Analisis de datos
    * Es el que permite ver como funciona el sistema que opera en la empresa.