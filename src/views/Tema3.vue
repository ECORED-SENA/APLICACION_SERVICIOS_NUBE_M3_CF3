<template lang="pug">
.curso-main-container.pb-3
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5
    .titulo-principal
      .titulo-principal__numero
        span  3
      h1 SQL Para la manipulación de datos - DML

    .clearfix
    br
    .row.justify-content-center.mb-5
      .col-lg-10.slideInUp
        .tarjeta-avatar-b.mb-4.custom-card
          .tarjeta.light-yellow.shadow-box
            .p-5
              p.mb-3 Una base de datos sin datos no es muy útil, de manera que <b>se verá cómo añadir, modificar o eliminar los datos que poseen las bases de datos.</b>

          img(src='@/assets/curso/t3-i1.svg' alt='imagen decorativa')


    p.mb-5  Se creará una tabla con la que seguiremos <b>ejemplificando la sintaxis del SQL.</b>
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t3-c1.png' alt='ejemplo de tabla') 

    Separador
    br
    br        

    #t_3_1.titulo-segundo
      h2 3.1  Inserción de registros
    p.mb-5  La forma más directa de implantar una fila nueva en una tabla es por medio de una sentencia INSERT. De la manera más sencilla de esta sentencia se debe indicar la tabla a la que se quiere agregar filas, y los valores de cada columna. Las columnas de tipo cadena o fechas tienen que estar entre comillas sencillas o dobles,  esto no es obligatorio para las columnas numéricas, aunque también pueden estar entrecomilladas.
    .row.justify-content-center.mb-5
      .col-lg-10
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t3-c2.png' alt='ejemplo de tabla') 

    p.mb-5  Si no se requiere determinar un valor preciso para alguna columna, se puede determinar el valor por defecto indicado para esa columna cuando la tabla fue creada, usando la palabra
      span.etiqueta DEFAULT:
    .row.justify-content-center.mb-5
      .col-lg-10
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t3-c3.png' alt='ejemplo de tabla') 
    
    p.mb-5  Mire como Perillo tiene el valor por defecto definido en la columna fecha y edad.
    .row.justify-content-center.mb-5
      .col-lg-10
        .tarjeta--gris.p-4.text-left
          figure
            img.nW(src='@/assets/curso/t3-c4.png' alt='ejemplo de tabla') 

    p.mb-5  El orden en la sentencia INSERT es muy importante, conserve una correspondencia como se muestra en la siguiente imagen.
    .row.justify-content-center.mb-5
      .col-lg-11
        figure
          img.nW(src='@/assets/curso/t3-c5.png' alt='ejemplo de tabla') 

    p.mb-5  Finalmente, estamos listos para aprender cómo se actualizan los datos que se han registrado.



    Separador
    br
    br  
    #t_3_2.titulo-segundo
      h2 3.2  Edición de registros
    p.mb-5  Tenemos la posibilidad de cambiar valores de las filas de una tabla utilizando la sentencia 
      span.etiqueta UPDATE. 
      | En su manera más fácil, los cambios se usan a cada una de las filas, y a las columnas que se les especifique.
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t3-c6.png' alt='ejemplo de tabla') 
        figcaption  Nota: MySQL 8.0 Reference Manual, 2021
    p.mb-5  Que todas las personas de la tabla gente tengan la misma fecha utilizando esta sentencia 
      span.etiqueta UPDATE
    .row.justify-content-center.mb-5
      .col-lg-10
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t3-c7.png' alt='ejemplo de tabla') 
    p.mb-5  Al suponer que se necesita ponerle el incrementar la edad por 10 años a cada fila de la tabla gente:
    .row.justify-content-center.mb-5
      .col-lg-10
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t3-c8.png' alt='ejemplo de tabla') 

    p.mb-5  Sin embargo no se tienen que actualizar todas filas de la tabla, ya que se tiene la posibilidad de definir cuales filas se desean actualizar.
    p.mb-5  La primera es por medio de la cláusula 
      span.etiqueta WHERE. 
      | Utilizando esta cláusula se tiene la posibilidad de entablar una condición. Únicamente las filas que cumplan dicha condición van a ser actualizadas:
    .row.justify-content-center.mb-5
      .col-lg-10
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t3-c9.png' alt='ejemplo de tabla') 
            
    p.mb-5  Otro ejemplo sería que se actualice la fecha al día 2012-12-12 para todos lo que sean mayores de 40 años de edad, esto se podría hacer así: 
    .row.justify-content-center.mb-5
      .col-lg-10
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t3-c10.png' alt='ejemplo de tabla') 



    Separador
    br
    br  
    #t_3_3.titulo-segundo
      h2 3.3 Borrado de registros
    p.mb-5  Para borrar filas se utiliza la sentencia 
      span.etiqueta DELETE. 
      | La sintaxis es muy similar a la de 
      span.etiqueta UPDATE:
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t3-c11.png' alt='ejemplo de tabla') 

    p.mb-5  Para borrar el registro que tiene por nombre Perillo se procede de la siguiente forma.
    .row.justify-content-center.mb-5
      .col-lg-10
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t3-c13.png' alt='ejemplo de tabla') 

    p.mb-5  A continuación, se debe borrar aquello que tenga edad comprendida entre 30 (incluyendo 30) y 50 años (incluyendo 50), para eso se usa un operador llamado 
      span.etiqueta AND, 
      | se verán con más detalle estos operadores.
    .row.justify-content-center.mb-5
      .col-lg-10
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t3-c14.png' alt='ejemplo de tabla') 
        figcaption  Nota: MySQL 8.0 Reference Manual, 2021
    .cajon.color-acento-botones.p-4.mb-5
      .h5 Vaciar una tabla
      p Cuando se deseen borrar todas las filas de una tabla, se puede utilizar una sentencia DELETE sin condiciones, como se vio en el punto anterior. Pero existe una sentencia alternativa, TRUNCATE, que hace la misma tarea de una forma mucho más veloz. La diferencia es que DELETE hace un borrado secuencial de la tabla, fila por fila y  TRUNCATE elimina la tabla y la vuelve a crear desocupada, lo que es mucho más eficaz.
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t3-c15.png' alt='ejemplo de tabla') 







</template>

<script>
export default {
  name: 'Tema3',
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
.h180{max-height: 180px}
.h300{max-height: 300px}
.h600{max-height: 600px}
</style>
