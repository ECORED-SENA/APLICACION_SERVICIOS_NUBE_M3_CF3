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
          img(src='@/assets/curso/t2-c6.svg' alt='ejemplo de tabla')    








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

<style lang="sass" scoped></style>
