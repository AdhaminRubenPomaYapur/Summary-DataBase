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
    3. Cardinalidad.- Es la cantidad de filas relacionadas de cada uno de los objetos en la relacion.

        1. Uno a uno        (1-1)
        2. Uno a muchos     (1-N)
        3. muchos a muchos  (N-M)
        4. Cardinalidad obligatoria
        5. Cardinalidad opcional
***
# 3. (DBMS) Data base Management System
    * Es un conjunto de componentes que soportan la creacion, el uso y el mantenimiento de base de datos inicialmente. Proporcionan almacenamiento y recuperacion de datos.
    
        *
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
