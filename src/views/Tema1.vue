<template lang="pug">
.curso-main-container.pb-3
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5
    .titulo-principal
      .titulo-principal__numero
        span  1
      h1 Interface de Línea de Comandos de MySQL

    .row.justify-content-center.mb-5
      .col-lg-10
        .bloque-texto-a.color-secundario.p-4.p-md-5.variant1.slideInUp 
          .row.m-0.align-items-center.justify-content-between
            .col-lg-3.mb-4.mb-lg-0
              figure.mb-5
                img(src="@/assets/curso/t1-i1.svg", alt="logo de MySQL")

            .col-lg-9
              .bloque-texto-a__texto.p-4
                p.mb-3  Al iniciar a trabajar con el SGBD, existen varias maneras de enlazar una comunicación con el servidor de MySQL. Generalmente en el software, se usará un API para hacer las consultas y otras operaciones con el servidor. <b>Por ejemplo, en PHP, esta API está integrada con el lenguaje.</b>
                p.mb-3  En este punto se usará MySQL de forma directa, por medio de un cliente ejecutándose desde una consola (una ventana de comandos en Windows). <b>En otras secciones se explicarán los distintos APIs.</b>

    #t_1_1.titulo-segundo
      h2 1.1  Aplicación cliente de MySQL
    p.mb-5  Se debe seguir las siguientes instrucciones para conectarse a la base de datos a través del cliente de línea de comandos. 
    .row.justify-content-center
      .col-lg-10
        PasosA.color-acento-contenido.mb-5(tipo="n")
          .row.py-4
            .col-md-6.mb-4.mb-md-0
              p Debe abrir inicio y <b>buscar MySQL</b> o <b>teclear "mysql"</b> y se hace Clic en MySQL Command Line Client.
            .col-md-6
              figure(data-aos="flip-left", data-aos-delay='0')
                img.shadow-box(src='@/assets/curso/t1-i2.jpg', alt='captura de pantalla indicando donde hacer clic')

          .row.py-4
            .col-md-6.mb-4.mb-md-0
              figure(data-aos="flip-left", data-aos-delay='50')
                img.shadow-box(src='@/assets/curso/t1-i3.jpg', alt='ingresar contraseña de root')
            .col-md-6
              p Ingresa la contraseña de root usada en el proceso de instalación de MySQL.

          .row.py-4
            .col-md-6
              p Una vez autenticado en la interface comando de línea vemos este resultado
            .col-md-6.mb-4.mb-md-0
              figure(data-aos="flip-left", data-aos-delay='100')
                img.shadow-box(src='@/assets/curso/t1-i4.jpg', alt='ejemplo de linea de comandos')
    p.mb-5  En adelante los resultados de interface de línea de comandos se presentarán como sigue:
    .row.mb-5.justify-content-center
      .col-lg-8
        .tarjeta--gris.p-4
          code
            Enter password: *********** <br> Welcome to the MySQL monitor.  Commands end with; or \g.<br>Your MySQL connection id is 90<br>Server version: 8.0.25 MySQL Community Server - GPL<br><br> Copyright (c) 2000, 2021, Oracle and/or its affiliates.<br><br>Oracle is a registered trademark of Oracle Corporation and/or its<br> affiliates. Other names may be trademarks of their respective<br>owners.<br><br>Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.<br><br>mysql>
            
    p.mb-5  Para salir de la consola de comando se usa el comando quit (en mayúscula o minúscula)
    .row.mb-5.justify-content-center
      .col-lg-8
        .tarjeta--gris.p-4
          code
            | mysql
            span > 
            | QUIT <br> Bye<br> C:\mysql\bin> <br>

    Separador
    br
    br
    #t_1_2.titulo-segundo
      h2 1.2  Prueba de consultas básicas
    p.mb-5  Ya que se sabe entrar y salir del cliente <b>MySQL,</b> y  se tiene la posibilidad de realizar consultas. Lo más fácil es consultar varias variables del sistema o el valor de varias funcionalidades de <b>MySQL.</b> Para realizar esta clase de consultas se utiliza la sentencia SQL SELECT, por ejemplo:
    .row.mb-5.justify-content-center
      .col-lg-8
        .tarjeta--gris.p-4
          code  mysql&gt; SELECT VERSION (), CURRENT_DATE;<br>+-----------+--------------+<br>| VERSION () | CURRENT_DATE |<br>+-----------+--------------+<br>| 8.0.25    | 2021-06-12   |<br>+-----------+--------------+<br>1 row in set (0.02 sec)<br>mysql&gt;
          

    .row.mb-5
      .col-lg-7
        .cajon.color-acento-botones.p-4
          p <b>NOTA:</b> Toda sentencia debe finalizar con punto y coma (;), luego debe dar enter.        
            
    Separador        
    br
    br        
    #t_1_3.titulo-segundo
      h2 1.3  SQL – Standard Query Language
    p.mb-5  En nivel teórico, hay dos lenguajes para el uso de bases de datos:
    .tarjeta--container.row.mb-5
      .col-lg-6.tarjeta.c1.p-5
        .row.justify-content-center.mb-4.p-5.text-center
          .col-6
            figure.mb-5(data-aos="flip-left", data-aos-delay='0')
              img.h180(src='@/assets/curso/t1-x1.svg', alt='Imagen Decorativa')
          
          .h2 Data Definition Language
          p Es el lenguaje que se emplea para establecer bases de datos y tablas, y para transformar sus estructuras. Este lenguaje trabaja sobre ciertas tablas especiales llamadas diccionario de datos.

      .col-lg-6.tarjeta.c2.p-5
        .row.justify-content-center.mb-4.p-5.text-center
          .col-6
            figure.mb-5(data-aos="flip-right", data-aos-delay='100')
              img.h180(src='@/assets/curso/t1-x2.svg', alt='imagen decorativa')
          
          .h2 Data Manipulation Language
          p Es lo que se usa para cambiar y obtener datos desde las bases de datos.


    .row
      .col-lg-3
        figure
          img(src='@/assets/curso/t1-i7.svg', alt='imagen decorativa referente a usuario sentado usando un computador')        
      .col-lg-9   
        p.mb-3  <b>SQL</b> abarca ambos lenguajes <b>DDL+DML</b> y serán estudiados en esta unidad, ya que ambos hacen parte del conjunto de sentencias de <b>SQL.</b>
        p.mb-5  En este punto se explicará el proceso para convertir del modelo lógico relacional, al modelo físico, empleando sentencias SQL. <b>Ya no se empleará (por ahora), MySQL Workbeach, y se observarán las particularidades específicas de MySQL.</b>     
            

  
</template>

<script>
export default {
  name: 'Tema1',
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
