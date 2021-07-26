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
        figure(data-aos="fade-left", data-aos-delay='0')
          img(src='@/assets/curso/t4-i1.svg' alt='imagen decorativa') 
      .col-lg-9
        p.mb-3(data-aos="fade-right", data-aos-delay='50')  Para encontrar la información dentro de una base de datos, es preciso escudriñar dentro de la estructura de los datos su estructura y su naturaleza, por ejemplo, el tipo de datos fecha tiene una estructura YYYY-MM-DD,  y si necesito listar los registros de un año determinado, se necesita una función que refiera a ese dato particular dentro de la columna; por este motivo se necesita revisar algunas funciones antes de empezar a trabajar consultas de datos.
    #t_4_1.titulo-segundo
      h2 4.1  Funciones en MySQL
    .row.mb-5
      .col-lg-8
        p.mb-4  Considerando que MySQL es rico en lo que respecta a operadores y en lo que se refiere a funciones es también muy amplio, MySQL dispone de multitud de funciones. Sólo se explicarán algunas funciones necesarias para entender cómo funcionan en general.
        p.mb-4  Una lista completa de Funciones en MySQL, se puede encontrar en la siguiente referencia:
        a.anexo.mb-4.mb-lg-0(href="https://www.w3schools.com/mysql/mysql_ref_functions.asp" target="_blank")
          .anexo__icono
            img(src="@/assets/template/icono-link.svg")
          .anexo__texto
            p <b>Enlace web.</b> www.w3schools.com - MySQL Functions

      .col-lg-4
        figure(data-aos="fade-up", data-aos-delay='0')
          img(src='@/assets/curso/t4-i2.svg' alt='imagen decorativa') 

    p.mb-5  Se listarán las que se usarán en adelante para el ejemplo que sigue:
    .row.justify-content-center.mb-5
      .col-lg-10
        figure(data-aos="fade-up", data-aos-delay='0')
          img(src='@/assets/curso/t4-t1.svg' alt='tabla')


    p.mb-5 Para este ejemplo se usará una base de datos de llamadas telefónicas, esta base de datos tiene la estructura que se verá a continuación y con ella se aprenderá a hacer consultas.
    .row.mb-5.justify-content-center
      .col-lg-10 
        .cajon.color-acento-botones.p-4.mb-5
          .h4.mb-4 Ejemplo llamadas telefónicas:
          .row
            .col-lg-2
              figure
                img.h90(src='@/assets/curso/t4-i3.svg' alt='imagen decorativa') 
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
              pre.p-4.tarjeta--gris
                code  MariaDB [prueba]&gt; source D:/Peter/Downloads/cdr.sql;
        .tarjeta.color-primario.p-3.mb-5
          .row.justify-content-around.align-items-center
            .col-3.col-sm-2.col-lg-1
              img(src="@/assets/curso/t4-x2.svg")
            .col
              .row.justify-content-between.align-items-center
                .col.mb-3.mb-sm-0
                  h3.mb-1 Descargue aquí el archivo para crear la base de datos cdr. 
                .col-sm-auto
                  a.boton.color-acento-contenido(:href="obtenerLink('/downloads/CF3_4.1_cdr_sql.zip')" target="_blank")
                    span Descargar
                    i.fas.fa-file-download
    p.mb-5  Conozca los datos de prueba con los que se trabajará.
    .row.justify-content-center.mb-5
      .col-lg-10
        figure(data-aos="fade-up", data-aos-delay='0')
          img(src='@/assets/curso/t4-t2.svg' alt='tabla')

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
            img.nW(src='@/assets/curso/t4-c1.png' alt='ejemplo de tabla') 
        figcaption  MySQL 8.0 Reference Manual (2021).

    p.mb-5 Para listar todos los elementos de la tabla se debe usar la sentencia:
    .row.justify-content-center.mb-5
      .col-lg-10
        .card-outlined-blue.p-4.mb-4
          .row
            .col-lg-8
              .tarjeta--gris.p-4.mb-5
                figure
                  img.nW(src='@/assets/curso/t4-p1.png' alt='ejemplo de tabla') 
              p.mb-5  Escriba la sentencia anterior. Al decir *  estamos diciendo que seleccione todas las columnas de la tabla cdr:
            .col-lg-4
              figure
                img(src='@/assets/curso/t4-i8.jpg' alt='captura de pantalla indicando donde hacer clic') 

        .card-outlined-blue.p-4
          .row
            .col-lg-8
              .tarjeta--gris.p-4.mb-5
                p.mb-5  También se pueden seleccionar solo algunas, para esto, se deben separar por una coma así:
                figure
                  img.nW(src='@/assets/curso/t4-p2.png' alt='ejemplo de tabla') 
              
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
    p.mb-5  Suponga que se necesita saber cuánto cobrar por las llamadas salientes realizadas a celular o larga distancia nacional (que el destino tenga 10 dígitos), sabiendo que el valor del minuto son $85 (ochenta y cinco pesos):
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

    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img.nW(src='@/assets/curso/t4-c3.svg' alt='ejemplo de tabla') 

    .row.justify-content-center
      .col-lg-10
        TabsA.color-acento-botones.mb-5.custom-labels
          //- .tarjeta debe ir acompañado de una de una de estas clases => 
          //- .color-primario, .color-secundario, .color-acento-contenido, .color-acento-botones
          //- estas clases tambien tienen un modificador --borde
          .tarjeta.color-acento-botones--borde.p-5(titulo="Operador AND")
            h3.mb-4.etiqueta Operador AND
            p.mb-3  SQL se puede usar el operador AND, que se trata de un operador binario, es decir, requiere de dos operandos. El resultado de la operación es verdadero, sólo si ambos operandos son verdaderos, falso si cualquier operando es falso o nulo si alguno de los dos es nulo. 
            p.mb-5  Esto se representa mediante la siguiente tabla de verdad:
            .tabla-a.color-acento-botones.mb-4 
              table.table.text-center
                caption Nota: MySQL AND Operator By Examples (2020).
                thead
                  tr
                    th A
                    th B
                    th A AND B
                tbody
                  tr
                    td FALSO
                    td FALSO
                    td FALSO
                  tr
                    td FALSO
                    td VERDADERO
                    td FALSO
                  tr
                    td VERDADERO
                    td FALSO
                    td FALSO
                  tr
                    td VERDADERO
                    td VERDADERO
                    td VERDADERO
                  tr
                    td FALSO
                    td NULL
                    td FALSO
                  tr
                    td NULL
                    td FALSO
                    td FALSO
                  tr
                    td VERDADERO
                    td NULL
                    td NULL
                  tr
                    td NULL
                    td VERDADERO
                    td NULL
                    
            .tarjeta--gris.p-4
              figure
                img.nW(src='@/assets/curso/t4-c4.svg' alt='ejemplo de tabla') 


          .tarjeta.color-acento-botones--borde.p-5(titulo="Operador OR")
            h3.mb-4.etiqueta Operador OR
            p.mb-3  SQL este operador también tiene dos formas equivalentes OR  
            p.mb-4  El operador OR también es binario. Si ambos operandos siendo diferentes de NULL y el resultado es verdadero si alguno de ellos es verdadero y falso si los dos son falsos. Si uno de los operandos es NULL el resultado es verdadero si el otro es verdadero y NULL en el si el otro es falso. 
            p.mb-5  La tabla de verdad es
            .tabla-a.color-acento-botones.mb-4 
              table.table.text-center
                caption Nota: MySQL OR Operator (2020).
                thead
                  tr
                    th A
                    th B
                    th A OR B
                tbody
                  tr
                    td FALSO
                    td FALSO
                    td FALSO
                  tr
                    td FALSO
                    td VERDADERO
                    td VERDADERO
                  tr
                    td VERDADERO
                    td FALSO
                    td VERDADERO
                  tr
                    td VERDADERO
                    td VERDADERO
                    td VERDADERO
                  tr
                    td FALSO
                    td NULL
                    td NULL
                  tr
                    td NULL
                    td FALSO
                    td NULL
                  tr
                    td VERDADERO
                    td NULL
                    td VERDADERO
                  tr
                    td NULL
                    td VERDADERO
                    td VERDADERO
            .tarjeta--gris.p-4
              figure
                img.nW(src='@/assets/curso/t4-c4-1.svg' alt='ejemplo de tabla') 
    h3.titulo-tercero
        span.squareLetter B
        | Operadores de igualdad+
    .row.justify-content-center.mb-3
      .col-lg-10    
        p  El operador igual (=) compara dos expresiones y da como resultado TRUE si son iguales o FALSE si son diferentes. Ya lo hemos usado en ejemplos anteriormente:
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          pre
            code  SELECT * FROM cdr  WHERE registro = '2018-01-02 10:19:08'

    h3.titulo-tercero
        span.squareLetter C
        | Operadores de desigualdad
    .row.justify-content-center.mb-5
      .col-lg-5
        .tabla-a.color-acento-botones.mb-4 
          table.table.text-center
            caption Nota: MySQL OR Operator (2020).
            thead
              tr
                th Operador
                th Descripción
            tbody
              tr
                td &lt;=
                td Menor o igual
              tr
                td &lt;
                td Menor
              tr
                td &gt;
                td Mayor
              tr
                td &gt;=
                td Mayor o igual                
        .tarjeta--gris.p-4
          pre
            code SELECT * FROM cdr <br>WHERE registro &gt;= '2018-01-02 10:19:08' <br>AND registro &lt;= '2018-01-04 10:19:08'


      .col-lg-5
        figure
          img.shadow-box(src='@/assets/curso/t4-i12.jpg' alt='ejemplo de tabla') 
    
    Separador
    br
    br
    #t_4_3.titulo-segundo
      h2 4.3  Ordenar resultados
    .row.mb-4
      .col-lg-3
        figure
          img(src='@/assets/curso/t4-i12-1.svg' alt='ejemplo de tabla') 
      .col-lg-9
        p.mb-5  También, se puede agregar una cláusula de   para lograr resultados ordenados por la columna que se quiera y se puede hacer ascendente o descendente con la cláusula ASC y DESC respectivamente.
        p.mb-5  Por ejemplo se desea listas las llamadas en orden de duración descendente (de mayor a menor):
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          pre
            code SELECT * FROM cdr ORDER BY duracion DESC
    .row.justify-content-center.mb-5
      .col-lg-6
        figure
          img.shadow-box(src='@/assets/curso/t4-i13.jpg' alt='ejemplo de tabla') 
    p.mb-5  Y también de manera ascendente por la fecha: 
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          pre
            code SELECT * FROM cdr ORDER BY registro ASC
    .row.justify-content-center.mb-5
      .col-lg-6
        figure
          img.shadow-box(src='@/assets/curso/t4-i14.jpg' alt='ejemplo de tabla')     
    p.mb-5  También se puede ordenar por el resultado de operación, aunque el rendimiento de la consulta disminuye. Ejemplo, para llamadas de larga distancia o celular a 85 pesos el minuto, que se ordene por la llamada que más costo tenga a la que menos costo tenga.
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          pre
            code SELECT *, CEIL(facturar/60) * 85 AS valor FROM cdr<br>WHERE LENGTH(destino) = 10 <br>ORDER BY  CEIL(facturar/60) * 85  DESC
    .row.justify-content-center.mb-5
      .col-lg-6
        figure
          img.shadow-box(src='@/assets/curso/t4-i15.jpg' alt='ejemplo de tabla')    

    p.mb-5 Se puede agrupar por varios criterios a la vez, por ejemplo si se ordenan los resultados por la duración y si hay repetidos, que el siguiente criterio sea la fecha de registro. 
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          pre
            code SELECT * FROM cdr<br>ORDER BY  facturar  DESC , registro  ASC
    .row.justify-content-center.mb-5
      .col-lg-6
        figure
          img.shadow-box(src='@/assets/curso/t4-i15.jpg' alt='ejemplo de tabla')    

    Separador
    br
    br

    #t_4_4.titulo-segundo
      h2 4.4  Listar y limitar resultados
    .row.mb-4
      .col-lg-3
        figure
          img(src='@/assets/curso/t4-i17.svg' alt='imagen decorativa') 
      .col-lg-9
        p.mb-5  La principal forma de limitar resultados es filtrando condiciones en los datos con la cláusula 
          span.etiqueta WHERE, 
          | sin embargo cuando a pesar de eso los datos son muchos, es necesario paginarlo o presentarlo por partes, para ello se miraría la cláusula 
          span.etiqueta LIMIT. 
        p.mb-5  <b>Ejemplo:</b> se desea filtrar las llamadas larga distancia o celular de todo el año 2016 que cuestan más de $1.000, y presentarlas ordenadas de mayor a menor por el precio.
    .row.justify-content-center.mb-5
      .col-lg-5
        .tarjeta--gris.p-4
          pre
            code SELECT *, CEIL(facturar/60) * 85 AS valor<br>FROM cdr<br>WHERE YEAR(registro) = 2016<br>AND LENGTH(destino) = 10<br>AND CEIL(facturar/60) * 85 &gt; 200<br>ORDER BY valor DESC
      .col-lg-5
        figure
          img.shadow-box(src='@/assets/curso/t4-i18.jpg' alt='captura de pantalla lineas de código') 
    p.mb-5  Los datos que la consulta arroja seguramente son muchos. Para saber cuántos resultados cumplen con las condiciones de la cláusula 
      span.etiqueta WHERE, 
      | es preciso contarlos con la función 
      span.etiqueta COUNT, 
      | pero la consulta no debe usar la cláusula 
      span.etiqueta ORDER BY 
      | porque la función 
      span.etiqueta COUNT 
      | solamente arroja una fila y con una única columna, por lo tanto, el resultado no se puede ordenar.
    .row.justify-content-center.mb-5
      .col-lg-5
        .tarjeta--gris.p-4
          pre
            code SELECT COUNT(*)<br>FROM cdr<br>WHERE YEAR(registro) = 2016<br>AND LENGTH(destino) = 10<br>AND CEIL(facturar/60) * 85 &gt; 200
      .col-lg-5
        figure
          img.shadow-box(src='@/assets/curso/t4-i19.jpg' alt='captura de pantalla lineas de código') 
   
    p.mb-5  Como se pueden ver son muchos registros, pero si el interés es mostrar los primeros10, utilice la cláusula 
      span.etiqueta LIMIT.
    .row.justify-content-center.mb-5
      .col-lg-5
        .tarjeta--gris.p-4
          pre
            code SELECT COUNT(*)<br>FROM cdr<br>WHERE YEAR(registro) = 2016<br>AND LENGTH(destino) = 10<br>AND CEIL(facturar/60) * 85 &gt; 200
      .col-lg-5
        figure
          img.shadow-box(src='@/assets/curso/t4-i20.jpg' alt='captura de pantalla lineas de código') 

    p.mb-5  Para lograr hacer esto la cláusula 
      span.etiqueta LIMIT 
      | permite dos parámetros. Cuando se utilizan los dos, el primero muestra el número de la primera fila a traer, y el segundo el número de filas a traer. Se puede por ejemplo, rescatar las filas de dos en dos:
    .row.justify-content-center.mb-5
      .col-lg-5
        .tarjeta--gris.p-4
          pre
            code SELECT *, CEIL(facturar/60) * 85 AS valor <br>FROM cdr<br>WHERE YEAR(registro) = 2016<br>AND LENGTH(destino) = 10<br>AND CEIL(facturar/60) * 85 &gt; 200<br>ORDER BY valor DESC<br>LIMIT 10, 10
      .col-lg-5
        figure
          img.shadow-box(src='@/assets/curso/t4-i21.jpg' alt='captura de pantalla lineas de código') 

    p.mb-5 Y con la siguiente consulta se traen los próximos 10
    .row.justify-content-center.mb-5
      .col-lg-5
        .tarjeta--gris.p-4
          pre
            code SELECT *, CEIL(facturar/60) * 85 AS valor<br>FROM cdr<br>WHERE YEAR(registro) = 2016<br>AND LENGTH(destino) = 10<br>AND CEIL(facturar/60) * 85 &gt; 200<br>ORDER BY valor DESC<br>LIMIT 20, 10
      .col-lg-5
        figure
          img.shadow-box(src='@/assets/curso/t4-i22.jpg' alt='captura de pantalla lineas de código') 


    Separador
    br
    br

    #t_4_5.titulo-segundo
      h2 4.5  Agrupar Filas
    .row.mb-4
      .col-lg-3
        figure
          img(src='@/assets/curso/t4-i23.svg' alt='imagen decorativa') 
      .col-lg-9
        p.mb-5  Se pueden agrupar filas en la salida con la sentencia 
          span.etiqueta SELECT, 
          | según los valores de una columna, usando la cláusula 
          span.etiqueta GROUP BY. 
          | Y se usa con funciones de agrupación como lo son, 
          span.etiqueta AVG, SUM, MAX, COUNT, 
          | entre otros.
        p.mb-5  <b>Ejemplo:</b> se desea saber cuántas llamadas entrantes se realizaron durante cada uno de los meses del año 2017. Las llamadas entrantes son aquellas que no provienen de una extensión local, es decir, el origen tiene más de tres dígitos.

    .row.justify-content-center.mb-5
      .col-lg-6
        .tarjeta--gris.p-4
          pre
            code SELECT MONTH(registro) AS mes, COUNT(*) AS cantidad<br>FROM cdr<br>WHERE LENGTH(origen) &gt; 3 AND YEAR(registro) = 2017<br>GROUP BY mes
      .col-lg-5
        figure
          img.shadow-box(src='@/assets/curso/t4-i24.jpg' alt='captura de pantalla lineas de código') 
    p.mb-5  Pero si se desea mostrar también la agrupación de los años 2017, 2018 y 2019 y los meses de cada uno de estos años la sería:
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          pre
            code SELECT YEAR(registro) AS año,  MONTH(registro) AS mes, COUNT(*) AS cantidad<br>FROM cdr<br>WHERE LENGTH(origen) &gt; 3 AND YEAR(registro) IN (2017,2018,2019)<br>GROUP BY año, mes<br>ORDER BY año, mes
    p.mb-5  Es de resaltar que para agregar más de una opción en el año, se usó la cláusula IN y se ordena por año y como segundo criterio por mes.
    .row.justify-content-center.mb-5  
      .col-lg-6
        figure
          img.shadow-box(src='@/assets/curso/t4-i25.jpg' alt='captura de pantalla lineas de código')     













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

<style lang="sass" scoped>
.h90{max-height: 90px}
</style>
