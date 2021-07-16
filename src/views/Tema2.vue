<template lang="pug">
.curso-main-container.pb-3
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5
    .titulo-principal
      .titulo-principal__numero
        span  2
      h1 SQL para la creación y eliminación de bases de datos - DDL
    .row.mb-5
      .col-lg-7.slideInUp
        p.mb-3  Cada grupo de entidades que tienen un modelo completo, forma una base de datos. Desde la perspectiva de SQL, una base de datos es únicamente un conjunto de relaciones (o tablas) y para organizarlas o diferenciarlas se accede a ellas por su nombre. A nivel de sistema operativo, cada base de datos se almacena en un directorio distinto por MySQL.
        p.mb-4  Por esto, crear una base de datos es un trabajo muy sencillo. Claro que, a la hora de crearla, la base de datos estará desocupada, es decir, no almacenará ninguna tabla.
        .cajon.color-acento-botones.p-4
          p.mb-3  <b>NOTA:</b> Es fundamental que mientras se estudia se ejecuten las sentencias propuestas aquí de esa manera se consolidarán los conocimientos de cada tema tratado.
          p.mb-3  Se debe tomar el tiempo necesario para escribir en la consola cada una de las sentencias, es un ejercicio fundamental para asimilar el conocimiento que se está adquiriendo.
          p.mb-3  De la misma forma se deben revisar los resultados que le da la ejecución, en caso de algún error en la sintaxis, la respuesta dará una idea de qué puede estar fallando.
      .col-lg-5.slideInRight
        figure
          img(src='@/assets/curso/t2-i1.svg' alt='imagen decorativa relacionada a persona sentada frente al computador')
    p.mb-3  Se va a <b>crear y manejar</b> una base de datos de práctica, a la vez que se familiarice con la manera de <b>trabajar de MySQL.</b>
    p.mb-5 Para iniciar, se creará una base de datos únicamente para practicar, y se llamará 
      span.etiqueta "prueba":
    TabsA.color-acento-botones.mb-5
      //- .tarjeta debe ir acompañado de una de una de estas clases => 
      //- .color-primario, .color-secundario, .color-acento-contenido, .color-acento-botones
      //- estas clases tambien tienen un modificador --borde
      .tarjeta.color-acento-botones--borde.p-5(titulo="PASO 1")
        p.mb-4  Se usa la sentencia 
          span.etiqueta  CREATE DATABASE 
          | para crear una base de datos.
        .row
          .col-lg-12
            .row.tarjeta--gris
              .col-lg-6
                .p-3
                  figure
                    img.nW(src='@/assets/curso/t2-c2.svg' alt='ejemplo de linea de comandos CREATE DATABASE')
      .tarjeta.color-acento-botones--borde.p-5(titulo="PASO 2")
        .row
          .col-lg-12
            p.mb-4  Se puede saber cuántas bases de datos se encuentran en nuestro sistema usando la sentencia 
              span.etiqueta SHOW DATABASES: 
          .col-lg-12
            .row.tarjeta--gris
              .col-lg-6
                .p-3
                  figure
                    img.nW(src='@/assets/curso/t2-c1.svg' alt='ejemplo de linea de comandos')
      .tarjeta.color-acento-botones--borde.p-5(titulo="PASO 3")
        .row
          .col-lg-12
            p.mb-4  Desde ahora, en los siguientes puntos, se trabajará con la base de datos creada, por lo cual, la elegirá como base de datos por defecto. Esto nos evitará poner el nombre de la base de datos en consultas. Para escoger una base de datos se emplea el comando
              span.etiqueta USE,
              | que no es puntualmente una sentencia SQL, sino una opción de MySQL: 
          .col-lg-12
            .row.tarjeta--gris
              .col-lg-6
                .p-3
                  figure
                    img.nW(src='@/assets/curso/t2-c2.svg' alt='ejemplo de linea de comandos USE')
      .tarjeta.color-acento-botones--borde.p-5(titulo="PASO 4")
        .row
          .col-lg-12
            p.mb-4  Para borrar una base de datos se usa la sentencia
              span.etiqueta SQL DROP.
              |  A continuación, se borrará la base de datos prueba, listaremos las existentes y la volveremos a crear.
          .col-lg-12
            .row.tarjeta--gris
              .col-lg-6
                .p-3
                  figure
                    img.nW(src='@/assets/curso/t2-c3.svg' alt='ejemplo de linea de comandos SQL DROP')
      .tarjeta.color-acento-botones--borde.p-5(titulo="PASO 5")
        .row
          .col-lg-12
            p.mb-4  Liste las bases de datos para comprobar que ya no existe la base de datos antes creada.
          .col-lg-12
            .row.tarjeta--gris
              .col-lg-6
                .p-3
                  figure
                    img.nW(src='@/assets/curso/t2-c4.svg' alt='ejemplo de linea de comandos para listar las bases de datos')

    
    #t_2_1.titulo-segundo
      h2 2.1  SQL para la creación y eliminación de Tablas
    .row.mb-5
      .col-lg-9
        p.mb-3  A continuación, la sentencia 
          span.etiqueta CREATE TABLE 
          | que se empleará para la creación de tablas.
        p.mb-3  Esta sentencia tiene una sintaxis algo compleja, ya que hay muchas opciones y se tienen varias posibilidades diferentes cuando se desea crear una tabla. Se irán viendo poco a poco y en breve tiempo se sabrá usar muchas de sus opciones.
        p.mb-3  En su forma más sencilla, 
          span.etiqueta CREATE TABLE 
          | hará una tabla con todas las columnas que le sean indicadas. A continuación un ejemplo, una tabla que admitirá almacenar el nombre de varias personas y las fechas de nacimiento de cada una. Se debe de indicar el nombre de la tabla, y los nombres de las columnas y tipos el tipo de datos de cada una de ella:

      .col-lg-3
        figure(data-aos="fade-up", data-aos-delay='50')
          img(src='@/assets/curso/t2-i2.svg' alt='imagen decorativa')
    p.mb-5  Se ha creará una tabla con el nombre de 
      span.etiqueta "gente" 
      | con dos columnas: 
      span.etiqueta "nombre" 
      | que puede aguantar cadenas de hasta 40 caracteres y 
      span.etiqueta "fecha" 
      | de tipo fecha.
    .row.justify-content-center.mb-5
      .col-lg-6.tarjeta--gris
        figure
          img(src='@/assets/curso/t2-c5.svg' alt='ejemplo de tabla')    
    p.mb-5 Se puede examinar cuántas tablas y qué nombres tienen en una base de datos, empleando la sentencia 
      span.etiqueta SHOW TABLES: 
    .row.justify-content-center.mb-5
      .col-lg-6.tarjeta--gris
        figure
          img.h210(src='@/assets/curso/t2-c6.svg' alt='ejemplo de tabla')    
    
    
    h3.titulo-tercero
        span.squareLetter A
        | Valores Nulos
    .row.mb-5.justify-content-center
      .col-lg-10
        p.mb-4  Al establecer cada columna se puede concluir si podrá o no contener valores nulos. Cabe recordar que, aquellas columnas que hacen parte de una clave primaria no pueden almacenar valores nulos.
        p.mb-4  Si se define una columna como clave primaria, queda imposibilitada para que pueda contener valores 
          span.etiqueta NULL (nulo), 
          | pero este caso no es únicamente en que se puede ser interesante imposibilitar la retribución de valores nulos para una columna.
        p.mb-5  Por defecto, cada columna permite valores nulos 
          span.etiqueta (NULL), 
          | y para que no se admitan, se usa 
          span.etiqueta NOT NULL. 
          | Por ejemplo:
        .row.justify-content-center.mb-5
          .col-lg-8
            .tarjeta--gris.p-4
              figure
                img.h210(src='@/assets/curso/t2-c7.svg' alt='ejemplo de tabla')         
        p.mb-5  Listar las tablas existentes hasta ahora:
        .row.justify-content-center.mb-5
          .col-lg-8
            .tarjeta--gris.p-4
              figure
                img.h210(src='@/assets/curso/t2-c8.svg' alt='ejemplo de tabla')         
    h3.titulo-tercero
        span.squareLetter B
        | Valores por defecto
    .row.mb-5.justify-content-center
      .col-lg-10
        p.mb-4  En una columna también se puede precisar, opcionalmente, un valor por defecto. El valor por defecto se determinará de forma automática a una columna a la hora que no se especifique un valor determinado al añadir.
        p.mb-4  Cuando una columna permite tener un valor nulo, y la hora de insertar no se especifica un valor, 
          span.etiqueta  NULL 
          | será usado como valor por defecto. En el anterior ejemplo, el valor por defecto para  
          span.etiqueta  poblacion 
          | es 
          span.etiqueta NULL.    
        p.mb-4  Por ejemplo, si se quiere que 50000 sea el valor que por defecto se pondrá en la columna 
          span.etiqueta  poblacion, 
          | Se creará la tabla como:
        p.mb-5  A continuación se debe escribir la sentencia,  pero esta vez se hará por partes.
        .row.justify-content-center.mb-5
          .col-lg-9
            .tarjeta--gris.p-4
              figure
                img.h210(src='@/assets/curso/t2-c9.svg' alt='ejemplo de tabla')  
        p.mb-5  Como la sentencia es larga se digitará por partes así:

        ol.lista-ol--cuadro.lista-ol--separador.mb-5
          li 
            .lista-ol--cuadro__vineta
              span 1
            p Primero se escribirá 
              span.etiqueta CREATE TABLE ciudad2 (nombre VARCHAR(20) NOT NULL,
          li 
            .lista-ol--cuadro__vineta
              span 2
            p.etiqueta Se presiona la tecla ENTER.
          li 
            .lista-ol--cuadro__vineta
              span 3
            p.etiqueta Luego se escribe el resto de la sentencia poblacion INT NULL DEFAULT 50000);           

        p.mb-5  Recuerde que MySQL interpreta una sentencia solo cuando encuentra el carácter punto y coma (;). El resultado será:
        .row.justify-content-center.mb-5
          .col-lg-9
            .tarjeta--gris.p-4
              figure
                img.h210(src='@/assets/curso/t2-c10.svg' alt='ejemplo de tabla')          
    h3.titulo-tercero
      span.squareLetter C
      | Claves Primarias
    .row.mb-5.justify-content-center
      .col-lg-10
        p.mb-4 Es posible definir una clave primaria sobre una columna, usando la palabra clave 
          span.etiqueta.text-bold PRIMARY KEY 
          | o 
          span.etiqueta.text-bold KEY.
        p.mb-4 En cada tabla únicamente puede haber una clave primaria, y la columna sobre la que se concreta una clave primaria no puede poseer valores 
          span.etiqueta NULL, 
          | como ya se hizo mención. Si esto no se especifica de forma explícita, MySQL lo hará de forma automática.
        p.mb-5 Por ejemplo, si se quiere crear un índice de la tabla de ciudad3 para la columna nombre, se creará la tabla así:
        .row.justify-content-center.mb-5
          .col-lg-9
            .tarjeta--gris.p-4
              figure
                img.h210(src='@/assets/curso/t2-c11.svg' alt='ejemplo de tabla')     
        p.mb-4  Emplear 
          span.etiqueta NOT NULL PRIMARY KEY, 
          | es lo mismo que 
          span.etiqueta PRIMARY KEY, NOT NULL KEY 
          | o simplemente 
          span.etiqueta KEY.
        p.mb-4  Hay una sintaxis distinta para crear claves primarias, que  generalmente es preferible, porque es más potente. De hecho, la que se ha explicado es un alias para la forma general, que no permite todas las funcionalidades (como, por ejemplo, crear claves primarias sobre varias columnas). 
        p.mb-5  Se verá esta otra alternativa un poco más adelante.

    h3.titulo-tercero
      span.squareLetter D
      | Columnas Autoincrementadas
    .row.mb-5.justify-content-center
      .col-lg-10
        p.mb-4  En MySQL existe la posibilidad de crear una columna autoincrementada, sin embargo, esta columna sólo puede ser de tipo entero y llave primaria.
        p.mb-4  Si cuando se inserta una fila se excluye el valor de la columna autoincrementada o si a un valor nulo se le intenta insertar para esa columna, su valor será calculado automáticamente, tomando el valor mayor de esa columna y sumándole uno, es decir, es secuencial. Permitiendo crear, una columna con un valor único y secuencias para cada fila de la tabla.
        p.mb-5  Comúnmente, estas columnas son usadas como claves primarias secuenciales. SQL solo las permite en números enteros, es decir una columna de otro timo no podrá ser autoincrementable, de tal forma que la composición de clave primaria, que sea entera y autoincrementada es perfecta para ser usada como clave primaria artificial:
        .row.justify-content-center.mb-5
          .col-lg-9
            .tarjeta--gris.p-4
              figure
                img.h210(src='@/assets/curso/t2-c12.svg' alt='ejemplo de tabla')    

    h3.titulo-tercero
      span.squareLetter E
      | Comentarios
    .row.mb-5.justify-content-center
      .col-lg-10
        p.mb-5  Adicionalmente, al momento de crear la tabla, se puede agregar un comentario a cada columna. Este comentario es usado como información adicional sobre una característica específica de la columna, y va en el apartado de documentación de la base de datos:
        .row.justify-content-center.mb-5
          .col-lg-9
            .tarjeta--gris.p-4
              figure
                img.h210(src='@/assets/curso/t2-c12-1.svg' alt='ejemplo de tabla')    

    h3.titulo-tercero
      span.squareLetter F
      | Descripción de la tabla
    .row.mb-5.justify-content-center
      .col-lg-10
        p.mb-3  SQL tiene una sentencia que permite ver la descripción de una tabla esta sentencia es 
          span.etiqueta DESC &lt;nombre_tabla&gt;
        .row.justify-content-center.mb-5
          .col-lg-9
            .tarjeta--gris.p-4
              figure
                img.h210(src='@/assets/curso/t2-c13.svg' alt='ejemplo de tabla')  

    h3.titulo-tercero
      span.squareLetter G
      | Documentación
    .row.mb-5.justify-content-center
      .col-lg-10
        p.mb-4  MySQL tiene una amplia documentación, se puede mirar el siguiente enlace para la sintaxis de crear una tabla antes de continuar <a href='https://dev.mysql.com/doc/refman/8.0/en/create-table.html' target='_blank'>https://dev.mysql.com</a>,  luego se podrá extraer una parte para ir estudiando poco a poco.
        p.mb-5  Pero SQL posee bastante opciones al momento de precisar columnas. También del tipo y el nombre, podemos concretar valores por defecto, admitir o no, que contengan valores tipo NULL, crear una clave primaria, indexar y muchas más. La sintaxis para definir las columnas es: 
        .row.justify-content-center.mb-5
          .col-lg-9
            .tarjeta--gris.p-4
              figure
                img.h210(src='@/assets/curso/t2-c14.svg' alt='ejemplo de tabla')
            figcaption  Nota: MySQL 8.0 Reference Manual (2021)  
        p.mb-5  Esta documentación se puede leer de la siguiente forma:
        .row.justify-content-center.mb-5
          .col-lg-8
            ul.lista-ul--color
              li 
                i.fas.fa-square
                span.etiqueta nombre_columna: 
                | es el nombre que se le dará a la columna a definir.
              li
                i.fas.fa-square
                | tipo_dato: es el tipo de datos de la columna 
                span.etiqueta  (INT, FLOAT, VAR CHAR).   
              li
                i.fas.fa-square
                p 
                  span.etiqueta [NOT NULL | NULL]: 
                  | todo lo que encuentre encerrado entre corchetes 
                  span.etiqueta ([]) 
                  | significa que es opcional pude incluirse o no, dentro de las opciones.<br>Lo que encuentre entre separado por el carácter pai 
                  span.etiqueta ( | ), 
                  | significa que debe escoger una opción de las que están paradas por el pai.
         
              li
                i.fas.fa-square
                p De esta manera se quiere definir un de que se llame 
                  span.etiqueta fecha 
                  | de tipo 
                  span.etiqueta DATE 
                  | y que no sea nuleable la sintaxis sería:

              .row.justify-content-center.mb-3
                .col-lg-12
                  .tarjeta--gris.p-4.mb-5
                    code  fecha DATE NOT NULL
                  p  Si quiero que el valor por defecto de esta columna sea la fecha actual del sistema puedo usar la sintaxis 
                    span.etiqueta DEFAULT CURRENT_DATE 
                    | así: 
              .row.justify-content-center.mb-5
                .col-lg-12
                  .tarjeta--gris.p-4
                    code  fecha DATE NOT NULL DEFAULT CURRENT_DATE       

    h3.titulo-tercero
      span.squareLetter H
      | Claves primarias compuestas

    .row.justify-content-center
      .col-lg-10
        p.mb-5  La sintaxis para concretar claves primarias es:
          .row.justify-content-center
            .col-lg-8
              .tarjeta--gris.p-4
                code  definición_columnas <br>  | PRIMARY KEY (index_nombre_col,...) 
              figcaption  Nota: MySQL 8.0 Reference Manual (2021)
        p.mb-5 Usando esta sintaxis, en el ejemplo anterior que se dio para crear claves primarias y quedaría de la siguiente forma:   
          .row.justify-content-center.mb-5
            .col-lg-8
              .tarjeta--gris.p-4
                figure
                  img(src='@/assets/curso/t2-c15.svg' alt='ejemplo de tabla')
        p.mb-4 Pero de esta manera, se tiene mayor cantidad de opciones, por ejemplo, entre los paréntesis se puede detallar diversos nombres de columnas, para construir claves primarias acomodadas por diversas columnas:
          .row.justify-content-center.mb-5
            .col-lg-8
              .tarjeta--gris.p-4
                figure
                  img(src='@/assets/curso/t2-c16.svg' alt='ejemplo de tabla')
        p.mb-4 Se puede observar como quedó definida la tabla, se debe prestar especial atención a la columna de salida llamada Key:
          .row.justify-content-center.mb-5
            .col-lg-8
              .tarjeta--gris.p-4
                figure
                  img(src='@/assets/curso/t2-c17.svg' alt='ejemplo de tabla')
    
    h3.titulo-tercero
      span.squareLetter I
      | Índices
    .row.justify-content-center
      .col-lg-10
        p.mb-3  Se tienen tres tipos de índices. El primero pertenece a las claves primarias, que como se vió, también se pueden crear en la parte de definición de columnas.
        p.mb-5  ¿Cuándo es oportuno crear índices?
        ol.lista-ol--cuadro
          li 
            span.lista-ol--cuadro__vineta A
            | Cuando se define una llave foránea.
          li 
            span.lista-ol--cuadro__vineta B
            | Cuando se sabe que se realizarán consultas directas sobre esa columna.
        p.mb-5 El segundo tipo de índice que existe, permite definir sobre una columna el índice. Para concretar estos índices se usan de manera indistinta las opciones 
          span.etiqueta KEY o INDEX.
        .row.justify-content-center.mb-5
          .col-lg-8
            .tarjeta--gris.p-4
              figure
                img(src='@/assets/curso/t2-c18.svg' alt='ejemplo de tabla')      
        p.mb-5  O su semejante:
        .row.justify-content-center.mb-5
          .col-lg-8
            .tarjeta--gris.p-4
              figure
                img(src='@/assets/curso/t2-c19.svg' alt='ejemplo de tabla')      
    h3.titulo-tercero
      span.squareLetter J
      | Claves Únicas
    .row.justify-content-center
      .col-lg-10
        p.mb-4  El tercer tipo de índices es para crear claves únicas así mismo sobre una columna o sobre varias. Para definir índices con claves únicas se debe de usar la opción 
          span.etiqueta UNIQUE.
        p.mb-4  La diferencia entre un índice único y un índice normal, es que en los índices únicos no se admite la inclusión de filas con datos repetidos en la columna o columnas de la tabla. Una excepción es el valor 
          span.etiqueta NULL, 
          | que sí se puede llegar a repetir varias veces.  
        .row.justify-content-center.mb-5
          .col-lg-8
            .tarjeta--gris.p-4
              figure
                img(src='@/assets/curso/t2-c20.svg' alt='ejemplo de tabla')      
        p.mb-3  Los índices son útiles para optimizar las consultas y las búsquedas de datos. Por medio de su uso es mucho más eficiente encontrar filas con ciertos valores de columnas, o mostrar los resultados en cierto orden. La alternativa es realizar búsquedas secuenciales (sin índices), que en tablas extensas requieren mucho tiempo y procesamiento de datos.

    Separador
    br
    br

    #t_2_2.titulo-segundo
      h2 2.2  Claves foráneas

    p.mb-3  En MySQL únicamente existe soporte para claves foráneas en tablas de tipo InnoDB. 
    p.mb-5  InnoDB es el motor de almacenamiento por defecto de las últimas versiones de MySQL, no obstante, esto no imposibilita usarlas en otros tipos de tablas.
    .row.justify-content-center.mb-5
      .col-lg-6
        figure(data-aos="fade-up", data-aos-delay='50')
          img(src='@/assets/curso/t2-i3.png' alt='ejemplo de innoBD')   
    p.mb-5  Primero se crea la tabla persona:
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img(src='@/assets/curso/t2-c21.svg' alt='ejemplo de tabla')      
    p.mb-5  Si se quiere crear una base de datos que corresponda al modelo que se está presentando en la gráfica anterior las sentencias para la tabla teléfonos con la referencia a la tabla sería:
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img(src='@/assets/curso/t2-c22.svg' alt='ejemplo de tabla')      
   
    p.mb-4  Se ha usado una definición a modo referencia para la columna 
      span.etiqueta  “numero” 
      | de la tabla 
      span.etiqueta 'telefonos', 
      | señalando que es una clave foránea oportuna a la columna 
      span.etiqueta 'id_persona' 
      | de la tabla 
      span.etiqueta 'persona' 
      | a través de la columna 
      span.etiqueta  persona_id. 
      | No obstante, aunque la sintaxis se evidencia.  
    p.mb-4  La expresión 
      span.etiqueta  DELETE CASCADE 
      | , hace que, si se borra una fila de la tabla persona que tiene relacionados registros telefónicos a través de la columna 
      span.etiqueta persona_id 
      | en la tabla 
      span.etiqueta telefonos, 
      | estos registros (localizados en la tabla 
      span.etiqueta telefonos)
      | se borren si se borra el de la tabla 
      span.etiqueta persona,
      | a este tipo de condiciones se le llama restricción de integridad referencial.
    p.mb-4  De igual forma 
      span.etiqueta  UPDATE CASCADE
      | , hace que, si el 
      span.etiqueta id_persona 
      | en una fila de la tabla persona es actualizado a otro valor y existen referencias en la columna 
      span.etiqueta persona_id 
      | de la tabla 
      span.etiqueta telefonos 
      | con el valor inicial, al cambar el valor en el registro 
      span.etiqueta id_persona, 
      | cambien también el valor en los registros en la columna 
      span.etiqueta persona_id 
      | de la tabla 
      span.etiqueta telefonos. 
      | A este tipo de condiciones también se le llama restricción de integridad referencial.  
    p.mb-4  Y ejecutándola en la consola el resultado sería:
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img(src='@/assets/curso/t2-c23.svg' alt='ejemplo de tabla')      
    p.mb-4  Miremos otra variante de la misma sintaxis definiendo explícitamente que se usará el motor InnoDB para que las reglas de restricción de integridad apliquen:

    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img(src='@/assets/curso/t2-c24.svg' alt='ejemplo de tabla') 

    p.mb-5  Y también para la tabla 
      span.etiqueta telefonos2:
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img(src='@/assets/curso/t2-c25.svg' alt='ejemplo de tabla')      
    p.mb-5  Es necesario que la columna que posee una definición de clave foránea esté indexada 
      span.etiqueta KEY(numero). 
      | Sin embargo, esto no debe de generar preocupación, ya que si no se hace de forma clara, MySQL lo hará de forma implícita.
    p.mb-5  Dicha forma precisa una clave foránea en la columna 
      span.etiqueta persona_id, 
      | La cual hace referencia a la columna 
      span.etiqueta id_persona 
      | de la tabla 
      span.etiqueta personas2 (FOREIGN KEY (persona_id) REFERENCES personas2). 
      | La definición contiene las tareas a efectuar cuando se excluya una fila en la tabla 
      span.etiqueta personas2.
    .row.justify-content-center.mb-5
      .col-lg-5
        .boxTable
          .row.g-0
            .col-lg-12.light-yellow.d-flex.align-items-center
              .content-box.text-center.min-p
                .h3 
                  code
                    ON DELETE &lt;opcion&gt;,

            .col-lg-12.p-4
              p.mb-4 Define las acciones que deben de realizar en la tabla actual, <b>cuando se elimine una fila en la tabla referenciada.</b>
        

      .col-lg-5
        .boxTable
          .row.g-0
            .col-lg-12.light-yellow.d-flex.align-items-center
              .content-box.text-center.min-p
                .h3 
                  code
                    ON UPDATE &lt;opcion&gt;,

            .col-lg-12.p-4
              p.mb-4 Es semejante, define las acciones que deben de realizar en la tabla actual, <b>cuando se modifique o actualice la columna de una fila en la tabla referenciada.</b> 
    p.mb-5  Hay cinco opciones distintas. A continuación, lo que hace cada una de ellas:
    .row.justify-content-center
      .col-lg-10
        TabsA.color-acento-botones.mb-5.custom-labels
          //- .tarjeta debe ir acompañado de una de una de estas clases => 
          //- .color-primario, .color-secundario, .color-acento-contenido, .color-acento-botones
          //- estas clases tambien tienen un modificador --borde
          .tarjeta.color-acento-botones--borde.p-5(titulo="1. RESTRICT")
            h3.mb-4.etiqueta RESTRICT
            p Esta opción imposibilita borrar o editar filas en la tabla referenciada si hay filas con el mismo valor de clave foránea (MySQL 8.0 Reference Manual, 2021).
          .tarjeta.color-acento-botones--borde.p-5(titulo="2. CASCADE")
            h3.mb-4.etiqueta CASCADE
            p Borrar o modificar una clave en una fila en la tabla referenciada con un valor fijo de clave, conlleva borrar las filas con el mismo valor de clave foránea o cambiar los valores de esas claves foráneas (MySQL 8.0 Reference Manual, 2021).

          .tarjeta.color-acento-botones--borde.p-5(titulo="3. SET NULL")
            h3.mb-4.etiqueta SET NULL
            p Borrar o editar una clave en una fila en la tabla referenciada con un valor fijo de clave, involucra determinar el valor NULL a las claves foráneas con el mismo valor. (MySQL 8.0 Reference Manual, 2021)

          .tarjeta.color-acento-botones--borde.p-5(titulo="4. NO ACTION")
            h3.mb-4.etiqueta NO ACTION
            p Las claves foráneas no se alteran, ni se eliminan filas en la tabla que las contiene.

          .tarjeta.color-acento-botones--borde.p-5(titulo="5. SET DEFAULT")
            h3.mb-4.etiqueta SET DEFAULT
            p borrar o alterar una clave en una fila en la tabla referenciada con un valor explícito involucra asignar el valor por defecto a las claves foráneas con el mismo valor. (MySQL 8.0 Reference Manual, 2021)
    .row.mb-5
      .col-lg-3
        p.mb-5.text-bold  Ejemplo:
      .col-lg-7
        .tarjeta--gris.p-4
          figure
            img(src='@/assets/curso/t2-c26.svg' alt='ejemplo de tabla') 

    p.mb-4  Si se pretende borrar una fila de 
      span.etiqueta personas3 
      | con cierto valor de 
      span.etiqueta id_persona,
      | se provocará un error si existen filas en la tabla 
      span.etiqueta telefonos3 
      | en la columna 
      span.etiqueta persona_id 
      | con mismo valor. La fila de personas3 no será eliminada, a menos que previamente se eliminen las filas que tienen el mismo valor de clave foránea en la tabla 
      span.etiqueta teléfonos3, 
      | lo anterior debió que se ha definido restricción 
      span.etiqueta DELETE RESTRICT.
    p.mb-4  Si se modifica el valor de la columna 
      span.etiqueta 'id_persona' 
      | en la tabla 
      span.etiqueta 'personas3', 
      | se modificarán los valores de la columna 
      span.etiqueta 'persona_id' 
      | para conservar la analogía.
    p.mb-5  Mirar los datos de las tablas 
      span.etiqueta personas3 
      | y 
      span.etiqueta telefonos3.

    .row.justify-content-center.mb-5
      .col-lg-5
        figcaption.customCaption.mb-2  Datos de la tabla 
            span.etiqueta personas3
        .tarjeta--gris.p-4.h-100
          figure
            img(src='@/assets/curso/t2-c27.svg' alt='ejemplo de tabla') 
      .col-lg-5
        figcaption.customCaption.mb-2  Datos de la tabla 
            span.etiqueta telefonos3
        .tarjeta--gris.p-4.h-100
          figure
            img(src='@/assets/curso/t2-c28.svg' alt='ejemplo de tabla') 

    p.mb-5  Si se intenta borrar la fila correspondiente a "Fulanito" se provocará un error, debido a que hay dos filas en 
    span.etiqueta 'teléfonos3' 
    | con el valor 1 en la columna 
    span.etiqueta 'persona_id'.
    p.mb-5  Sí será posible borrar la fila correspondiente a "Menganito", debido a que no existe fila alguna en la tabla 
    span.etiqueta3  'telefonos3' 
    | con el valor 2 en la columna 
    span.etiqueta 'persona_id'.
    p.mb-5  Si alteramos el valor de 
    span.etiqueta 'id_persona' 
    | en la fila conveniente a "Tulanito", por el valor 3, por ejemplo, se determinará el valor 3 a la columna 
    span.etiqueta 'persona_id' 
    | de las filas 3ª y 6ª de la tabla 
    span.etiqueta 'telefonos3':
    br
    br
    Separador
    br
    br
    #t_2_3.titulo-segundo
      h2 2.3  Mostrar y eliminar tablas y bases de datos
    p.mb-5  De vez en cuando es preciso eliminar una tabla, ya sea porque es más fácil crearla de nuevo que alterarla, o porque ya es prescindible.
    p.mb-5  Para borrar una tabla se usará la sentencia 
      span.etiqueta DROP TABLE.
    .row.justify-content-center.mb-5
      .col-lg-8.mb-5
        .tarjeta--gris.p-4
          code
            DROP TABLE [IF EXISTS] tbl_name [, tbl_name]
      .col-lg-8.mb-5
        .tarjeta--gris.p-4
          pre
            code mysql&gt; DROP TABLE telefonos2; <br>Query OK, 0 rows affected (0.75 sec)<br>mysql&gt;  
    p.mb-5  Se puede agregar las palabras
      span.etiqueta IF EXISTS
      | para impedir errores si la tabla a eliminar no existe.       
    .row.justify-content-center.mb-5     
      .col-lg-8.mb-5
        .tarjeta--gris.p-4
          pre
            code mysql&gt; DROP TABLE telefonos5;<br>ERROR 1051 (42S02): Unknown table 'telefonos5'<br>mysql&gt; DROP TABLE IF EXISTS telefonos5;<br>Query OK, 0 rows affected, 1 warning (0.00 sec)<br>mysql&gt;
    p.mb-5  De manera similar, se puede borrar bases de datos enteras, utilizando la sentencia 
      span.etiqueta DROP DATABASE. 
      | La sintaxis asimismo es muy sencilla, a continuación, se creará una base de datos, se creará una tabla y se borrará la base de datos.
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t2-c31.svg' alt='ejemplo de tabla') 
        figcaption  Nota: MySQL 8.0 Reference Manual (2021).
   
    .tarjeta-azul
      .row.py-5.my-5
        .col-lg-5
          figure
            img.h315(src='@/assets/curso/t2-i4.svg' alt='imagen decorativa relacionado a usuario y lineas de codigo') 
        .col-lg-7
          .titulo-segundo
            .h2 Ejercicios prácticos
          p.mb-5  Se propone que se revise y estudie dos ejercicios de repaso, que están en el documento adjunto “Ejercicios Prácticos”, en ellos  están completamente desarrollados dos ejercicios un poco más extensos, pero que recogen la temática hasta ahora vista, con la diferencia que los ejercicios propuestos <b>son más próximos a problemas de la vida real.</b>
          a.boton.color-acento-botones.me-3(:href="obtenerLink('/downloads/CF3_2.5_Ejercicios_Practicos.docx')" target="_blank")
            span Descargar
            i.fas.fa-file-download


  
      









</template>

<script>
export default {
  name: 'Tema2',
  data: () => ({
    // variables de vue
  }),
  mounted() {
    this.$nextTick(() => {
      this.$aosRefresh()
    })
  },
  updated() {
    this.$aosRefresh()
  },
}
</script>

<style lang="sass" scoped>
.h210{max-height: 210px}
.h315{max-height: 315px}
.tarjeta-azul{background-color: #E8F0F8}
</style>
