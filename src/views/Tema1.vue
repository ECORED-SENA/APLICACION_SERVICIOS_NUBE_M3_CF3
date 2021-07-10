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
        .bloque-texto-a.color-secundario.p-4.p-md-5 
          .row.m-0.align-items-center.justify-content-between
            .col-lg-3.mb-4.mb-lg-0
              figure.mb-5
                img(src="@/assets/curso/t1-i1.svg", alt="logo de MySQL")

            .col-lg-9
              .bloque-texto-a__texto.p-4
                p Think about all the possibilities. A good composition is the result of a hierarchy consisting of clearly contrasting elements set with distinct alignments containing irregular intervals of negative space. Nothing of without working at it. Be impossible to ignore.
                  br
                  br
                  | Stand so tall that they can’t look past you. Saul Bass on failure: Failure is built into creativity… the creative act involves this element of ‘newness’ and ‘experimentalism,’ then one must expect accept possibility of failure. 

    #t_1_1.titulo-segundo
      h2 1.1  Aplicación cliente de MySQL
    p.mb-5  Se debe seguir las siguientes instrucciones para conectarse a la base de datos a través del cliente de línea de comandos. 
    .row.justify-content-center
      .col-lg-10
        PasosA.color-primario.mb-5(tipo="n")
          .row.py-4
            .col-md-6.mb-4.mb-md-0
              p Debe abrir inicio y buscar MySQL o teclear "mysql" y se hace Clic en MySQL Command Line Client.
            .col-md-6
              figure
                img.shadow-box(src='@/assets/curso/t1-i2.jpg', alt='captura de pantalla indicando donde hacer clic')

          .row.py-4
            .col-md-6.mb-4.mb-md-0
              figure
                img.shadow-box(src='@/assets/curso/t1-i3.jpg', alt='ingresar contraseña de root')
            .col-md-6
              p Ingresa la contraseña de root usada en el proceso de instalación de MySQL.

          .row.py-4
            .col-md-6
              p Una vez autenticado en la interface comando de línea vemos este resultado
            .col-md-6.mb-4.mb-md-0
              figure
                img.shadow-box(src='@/assets/curso/t1-i4.jpg', alt='ejemplo de linea de comandos')
    p.mb-5  En adelante los resultados de interface de línea de comandos se presentarán como sigue:
    .row.mb-5.justify-content-center
      .col-lg-8
        .card.tarjeta--negra.p-4
          code
            Enter password: *********** <br> Welcome to the MySQL monitor.  Commands end with; or \g.<br>Your MySQL connection id is 90<br>Server version: 8.0.25 MySQL Community Server - GPL<br><br> Copyright (c) 2000, 2021, Oracle and/or its affiliates.<br><br>Oracle is a registered trademark of Oracle Corporation and/or its<br> affiliates. Other names may be trademarks of their respective<br>owners.<br><br>Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.<br><br>mysql>
            
    p.mb-5  Para salir de la consola de comando se usa el comando quit (en mayúscula o minúscula)
    .row.mb-5.justify-content-center
      .col-lg-8
        .card.tarjeta--negra.p-4
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
        .card.tarjeta--negra.p-4
          code
            | mysql
            span > 
            | QUIT <br> Bye<br> C:\mysql\bin> <br>

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
    //-- Aqui van los cards 60-60

    .row
      .col-lg-3
        figure
          img(src='@/assets/curso/t1-i7.svg', alt='imagen decorativa referente a usuario sentado usando un computador')        
      .col-lg-9   
        p.mb-3  <b>SQL</b> abarca ambos lenguajes <b>DDL+DML</b> y serán estudiados en esta unidad, ya que ambos hacen parte del conjunto de sentencias de <b>SQL.</b>
        p.mb-5  En este punto se explicará el proceso para convertir del modelo lógico relacional, al modelo físico, empleando sentencias SQL. <b>Ya no se empleará (por ahora), MySQL Workbeach, y se observarán las particularidades específicas de MySQL.</b>     
            
            
            
            











    //- El componente "Muestras" tiene las aplicaciones de todos los componentes de la base
    //- se encuentra en src/components/Muestras.vue
    //- Una vez el componente "Muestras" no se necesite 
    //- Se debe borrar el "import Muestras from '../components/Muestras'" y en "components" en "<script"
    //- esto evitará que se compile en la carpeta final de distribución
    Muestras
  
</template>

<script>
import Muestras from '../components/Muestras' // borrar una vez el componente "Muestras" no se necesite
export default {
  name: 'Tema1',
  components: {
    Muestras, // borrar una vez el componente "Muestras" no se necesite
  },
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
