<template lang="pug">
.curso-main-container.pb-3
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5
    .titulo-principal
      .titulo-principal__numero
        span  2
      h1 SQL para la creación y eliminación de bases de datos - DDL
    .row.mb-5
      .col-lg-7
        p.mb-3  Cada grupo de entidades que tienen un modelo completo, forma una base de datos. Desde la perspectiva de SQL, una base de datos es únicamente un conjunto de relaciones (o tablas) y para organizarlas o diferenciarlas se accede a ellas por su nombre. A nivel de sistema operativo, cada base de datos se almacena en un directorio distinto por MySQL.
        p.mb-4  Por esto, crear una base de datos es un trabajo muy sencillo. Claro que, a la hora de crearla, la base de datos estará desocupada, es decir, no almacenará ninguna tabla.
        .cajon.color-acento-botones.p-4
          p.mb-3  <b>NOTA:</b> Es fundamental que mientras se estudia se ejecuten las sentencias propuestas aquí de esa manera se consolidarán los conocimientos de cada tema tratado.
          p.mb-3  Se debe tomar el tiempo necesario para escribir en la consola cada una de las sentencias, es un ejercicio fundamental para asimilar el conocimiento que se está adquiriendo.
          p.mb-3  De la misma forma se deben revisar los resultados que le da la ejecución, en caso de algún error en la sintaxis, la respuesta dará una idea de qué puede estar fallando.
      .col-lg-5
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
                    img(src='@/assets/curso/t2-c2.svg' alt='ejemplo de linea de comandos CREATE DATABASE')
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
                    img(src='@/assets/curso/t2-c1.svg' alt='ejemplo de linea de comandos')
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
                    img(src='@/assets/curso/t2-c2.svg' alt='ejemplo de linea de comandos USE')
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
                    img(src='@/assets/curso/t2-c3.svg' alt='ejemplo de linea de comandos SQL DROP')
      .tarjeta.color-acento-botones--borde.p-5(titulo="PASO 5")
        .row
          .col-lg-12
            p.mb-4  Liste las bases de datos para comprobar que ya no existe la base de datos antes creada.
          .col-lg-12
            .row.tarjeta--gris
              .col-lg-6
                .p-3
                  figure
                    img(src='@/assets/curso/t2-c4.svg' alt='ejemplo de linea de comandos para listar las bases de datos')

    
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
        figure
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
          .row.justify-content-center.mb-5
            .col-lg-9
              .tarjeta--gris.p-4.mb-5
                code  fecha DATE NOT NULL
              p  Si quiero que el valor por defecto de esta columna sea la fecha actual del sistema puedo usar la sintaxis DEFAULT CURRENT_DATE así: 
          .row.justify-content-center.mb-5
            .col-lg-9
              .tarjeta--gris.p-4
                code  fecha DATE NOT NULL DEFAULT CURRENT_DATE       






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
</style>
