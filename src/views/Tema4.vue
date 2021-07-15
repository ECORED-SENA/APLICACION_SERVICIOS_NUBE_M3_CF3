<template lang="pug">
.curso-main-container.pb-3
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5
    .titulo-principal
      .titulo-principal__numero
        span  4
      h1 SQL para consulta de datos - DML
    .row.mb-5
      .col-lg-3
        figure
          img(src='@/assets/curso/t4-i1.svg' alt='imagen decorativa') 
      .col-lg-9
        p.mb-3  Para encontrar la información dentro de una base de datos, es preciso escudriñar dentro de la estructura de los datos su estructura y su naturaleza, por ejemplo, el tipo de datos fecha tiene una estructura YYYY-MM-DD,  y si necesito listar los registros de un año determinado, se necesita una función que refiera a ese dato particular dentro de la columna; por este motivo se necesita revisar algunas funciones antes de empezar a trabajar consultas de datos.
    #t_4_1.titulo-segundo
      h2 4.1  Funciones en MySQL
    .row.mb-5
      .col-lg-8
        p.mb-4  Considerando que MySQL es rico en lo que respecta a operadores y en lo que se refiere a funciones es también muy amplio, MySQL dispone de multitud de funciones. Sólo se explicarán algunas funciones necesarias para entender cómo funcionan en general.
        p.mb-4  Una lista completa de Funciones en MySQL, se puede encontrar en la siguiente referencia:
        a.anexo.mb-4.mb-lg-0(href="#!" target="_blank")
          .anexo__icono
            img(src="@/assets/template/icono-link.svg")
          .anexo__texto
            p <b>Enlace web.</b> Anexo. www.w3schools.com - MySQL Functions

      .col-lg-4
        figure
          img(src='@/assets/curso/t4-i2.svg' alt='imagen decorativa') 

      //-- Aqui viene la tabla


    p.mb-5 Para este ejemplo se usará una base de datos de llamadas telefónicas, esta base de datos tiene la estructura que se verá a continuación y con ella se aprenderá a hacer consultas.
    .row.mb-5.justify-content-center
      .col-lg-10 
        .cajon.color-secundario.p-4.mb-5
          .h4.mb-4 Ejemplo llamadas telefónicas:
          .row
            .col-lg-2
              figure
                img(src='@/assets/curso/t4-i3.svg' alt='imagen decorativa') 
            .col-lg-10
              ol.lista-ol--cuadro
                li 
                  .lista-ol--cuadro__vineta
                    span 1
                  | Descargue el archivo para crear la base de datos cdr (recuerde que debe descomprimirlo) y de él extraiga el archivo cdr.sql. Este archivo crea una base de datos llamadas cdr y dentro una tabla con el mismo nombre.
                li 
                  .lista-ol--cuadro__vineta
                    span 2
                  | Importe el archivo con la sentencia source 
                  span.etiqueta &lt;ruta del archivo sql&gt;.
              pre.p-4.color--gris
                code  MariaDB [prueba]&gt; source D:/Peter/Downloads/cdr.sql;
        .tarjeta.color-primario.p-3.mb-5
          .row.justify-content-around.align-items-center
            .col-3.col-sm-2.col-lg-1
              img(src="@/assets/componentes/ej-02.svg")
            .col
              .row.justify-content-between.align-items-center
                .col.mb-3.mb-sm-0
                  h3.mb-1 Descargue aquí el archivo para crear la base de datos cdr. 
                .col-sm-auto
                  a.boton.color-acento-contenido.texto-blanco(:href="obtenerLink('/downloads/prueba.pdf')" target="_blank")
                    span Descargar
                    i.fas.fa-file-download
    p.mb-5  Conozca los datos de prueba con los que se trabajará.
    //-- Aqui viene la tabla

    p.mb-5  A partir de este punto usaremos MySQL WorkBeach para visualizar mejor los resultados.

    TabsB.color-acento-botones.mb-5
      .py-4.py-md-5(titulo="Paso 1" :icono="require('@/assets/curso/t4-ic1.svg')")
        .row
          .col-md-6.mb-4.mb-md-0
            ol.lista-ol--cuadro
              li 
                .lista-ol--cuadro__vineta
                  span 1
                | De clic en la pestaña de uso de bases de datos.
              li 
                .lista-ol--cuadro__vineta
                  span 2
                | Cree una nueva conexión.
              li 
                .lista-ol--cuadro__vineta
                  span 3
                | Póngale un nombre que usted prefiera a esa conexión.
              li 
                .lista-ol--cuadro__vineta
                  span 4
                | Ponga el usuario root.
              li 
                .lista-ol--cuadro__vineta
                  span 5
                | Digite el nombre de la base de datos que usará: cdr.
              li 
                .lista-ol--cuadro__vineta
                  span 6
                | Dele clic en ok.

        
          .col-md-6
            figure
              img.shadow-box(src='@/assets/curso/t4-i5.jpg', alt='ventana de dialogo MySQL workbench')

      .py-4.py-md-5(titulo="Paso 2" :icono="require('@/assets/curso/t4-ic2.svg')")
        .row
          .col-md-4.mb-4.mb-md-0
            ol.lista-ol--cuadro
              li 
                .lista-ol--cuadro__vineta
                  span 7
                | Ahora debe conectar dando doble clic.
          .col-md-4
            figure
              img.shadow-box(src='@/assets/curso/t4-i6.jpg', alt='ventana de dialogo MySQL workbench')
          .col-md-4
            figure
              img.shadow-box(src='@/assets/curso/t4-i7.jpg', alt='ventana de dialogo MySQL workbench')
    p.mb-5  Ya se dispone de bases de datos y se sabe cómo agregar y cambiar datos. A continuación se aprenderá a extraer datos de una base de datos. Para ello se volverá a utilizar la sentencia 
      span.etiqueta SELECT.
    p.mb-5  La sintaxis de 
      span.etiqueta SELECT 
      | es complicada, Sin embargo, en este punto no se explicará todas sus opciones. Una manera más general reside en la siguiente sintaxis:  

    .row.mb-5.justify-content-center
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t4-c1.svg' alt='ejemplo de tabla') 
        figcaption  MySQL 8.0 Reference Manual (2021).

    p.mb-5 Para listar todos los elementos de la tabla se debe usar la sentencia:
    .row.justify-content-center.mb-5
      .col-lg-10
        .card-outlined-blue.p-4.mb-4
          .row
            .col-lg-8
              .tarjeta--gris.p-4.mb-5
                pre
                  code  SELECT * FROM cdr
              p.mb-5  Escriba la sentencia anterior. Al decir *  estamos diciendo que seleccione todas las columnas de la tabla cdr:
            .col-lg-4
              figure
                img(src='@/assets/curso/t4-i8.jpg' alt='captura de pantalla indicando donde hacer clic') 

        .card-outlined-blue.p-4
          .row
            .col-lg-8
              .tarjeta--gris.p-4.mb-5
                p.mb-5  También se pueden seleccionar solo algunas, para esto, se deben separar por una coma así:
                pre
                  code  SELECT origen, destino, duracion FROM cdr
              
            .col-lg-4
              figure
                img(src='@/assets/curso/t4-i9.jpg' alt='captura de pantalla indicando donde hacer clic') 
    
    p.mb-5  También cabe mencionar que es posible asignar un alias a cualquiera de las expresiones 
      span.etiqueta SELECT 
      | y se puede realizar empleando la palabra AS aunque esta palabra es opcional:

    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4.mb-5
          pre
            code  SELECT origen AS num_orig, destino, duracion AS tiempo_llamada FROM cdr
        figure
          img(src='@/assets/curso/t4-i10.jpg' alt='captura de pantalla indicando donde hacer clic') 
    p.mb-5  Para lisSuponga que se necesita saber cuánto cobrar por las llamadas salientes realizadas a celular o larga distancia nacional (que el destino tenga 10 dígitos), sabiendo que el valor del minuto son $85 (ochenta y cinco pesos):
    p.mb-5  Lo primero que se necesita tener en cuenta, es que hay que filtrar las llamadas que tienen un destino de 10 dígitos. Esto se logra con la función 
      span.etiqueta LENGTH 
      | y el número de segundos que tiene la llamada desde que es atendida, se guarda en la columna 
      span.etiqueta facturar. 
      | Pero para saber cuántos minutos duró la llamada, se debe dividir el número de segundos por 60 y eso nos da el número de minutos. Ahora, el número de minutos no es entero y tiene datos decimales se debe redondear hacia arriba con la función 
      span.etiqueta CEIL 
      | y este valor ya redondeado, se puede multiplicar por 85 que es el valor del minuto. tar todos los elementos de la tabla se debe usar la sentencia:
    .row.mb-5.justify-content-center
      .col-lg-5
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t4-c2.svg' alt='ejemplo de tabla') 


      .col-lg-5
        figure
          img.shadow-box(src='@/assets/curso/t4-i11.jpg' alt='captura de pantalla') 

    Separador
    br
    br
    #t_4_2.titulo-segundo
      h2 4.2  Operadores    
    p.mb-5  SQL tiene muchos operadores diferentes según el tipo de columna. Esos operadores se emplean para construir expresiones que se usan en las consultas.
    h3.titulo-tercero
        span.squareLetter A
        | Operadores lógicos
    .row.justify-content-center
      .col-lg-10
        p.mb-4  Los operadores lógicos, se emplean para crear expresiones lógicas complejas. Permite el uso de álgebra booleana y ayuda a crear condiciones o filtros de información mucho más precisos.
        p.mb-4  Recuerde que en el álgebra booleana o álgebra de bool, existen dos valores posibles para ser operados y son los resultados: verdadero y falso. MySQL dispone de dos constantes para esos valores: 
          span.etiqueta TRUE
          | y 
          span.etiqueta FALSE, 
          | respectivamente.
        p.mb-4  En SQL se añade un tercer valor. Esto es para hacer posible trabajar con valores 
          span.etiqueta NULL. 
          | El valor verdadero se implementa como 1 o 
          span.etiqueta TRUE, 
          | el falso como 0 o 
          span.etiqueta FALSE 
          | y el desconocido como 
          span.etiqueta NULL.
        p.mb-5  Se ejecuta la siguiente sentencia en la consulta para que mirar la naturaleza de los datos.

    .row.justify-content-center
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t4-c3.svg' alt='ejemplo de tabla') 










</template>

<script>
export default {
  name: 'Tema4',
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
