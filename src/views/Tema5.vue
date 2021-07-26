<template lang="pug">
.curso-main-container.pb-3
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5
    .titulo-principal
      .titulo-principal__numero
        span  5
      h1 Consulta multitablas - DML
    .row.justify-content-center.mb-5
      .col-lg-10.slideInUp
        .bloque-texto-a.color-secundario.p-4.p-md-5 
          .row.m-0.align-items-center.justify-content-between
            .col-lg-7
              .bloque-texto-a__texto.p-4
                p Para explicar este tipo de ejercicios, crearemos una base de datos de empleados llamada ehr, y las tablas empleados y áreas, se relacionan si: un empleado pertenece a un área y un área puede tener varios empleados como se muestre en el siguiente diagrama:

            .col-lg-5.mb-4.mb-lg-0
              figure.mb-5
                img(src="@/assets/curso/t5-i1.png", alt="logo de MySQL")

    p.mb-5  Note que area_id en la tabla empleados puede ser nuleable:
    .row.justify-content-center.mb-5
      .col-lg-10
        .tarjeta--gris.p-4
          figure.mb-5
            img.nW(src="@/assets/curso/t5-c1.png", alt="Ejemplo de tabla")
    p.mb-5  Se insertarán los siguientes datos:
    .row.justify-content-center.mb-3
      .col-lg-10
        .tarjeta--gris.p-4
          figure.mb-5
            img.nW(src="@/assets/curso/t5-c2.png", alt="Ejemplo de tabla")
    .row.justify-content-center.mb-3
      .col-lg-10
        .tarjeta--gris.p-4
          figure.mb-5
            img.nW(src="@/assets/curso/t5-c3.png", alt="Ejemplo de tabla")
    .row.justify-content-center.mb-5
      .col-lg-10
        .tarjeta--gris.p-4
          figure.mb-5
            img.nW(src="@/assets/curso/t5-c4.png", alt="Ejemplo de tabla")            
    
    p.mb-5  Los datos quedan así:
    .row.justify-content-center.mb-5
      .col-lg-5
        .tabla-b__header.text-bold  Empleados
        .tarjeta--gris.p-4
          figure
            img.nW(src="@/assets/curso/t5-c5.png", alt="Ejemplo de tabla") 
      .col-lg-5
        .tabla-b__header.text-bold  Áreas
        .tarjeta--gris.p-4
          figure
            img.nW.mb-5(src="@/assets/curso/t5-c6.png", alt="Ejemplo de tabla") 


    #t_5_1.titulo-segundo
      h2 5.1  Combinación interna (INNER JOIN)
    .row.mb-4
      .col-lg-3
        figure(data-aos="fade-left", data-aos-delay='100')
          img(src='@/assets/curso/t5-i2.svg' alt='imagen decorativa') 
      .col-lg-9
        p.mb-5  Con esta operación, cada fila en la tabla empleados es combinada (o unida) con los correspondientes de la tabla areas que satisface la condición que se especifiquen en el predicado del JOIN. Cualquier fila de la tabla empleados o de la tabla areas que no tenga uno correspondiente en la otra tabla (areas) es excluido y solo aparecerán los que tengan correspondencia en la otra tabla. Este es el tipo de JOIN más utilizado, por lo que es considerado el tipo de combinación predeterminado. 
    .row.justify-content-center.mb-5
      .col-lg-6
        .tarjeta--gris.p-4
          figure
            img.nW(src="@/assets/curso/t5-c7.png", alt="Ejemplo de tabla")
      .col-lg-5
        figure
          img.shadow-box(src='@/assets/curso/t5-i3.jpg' alt='captura de pantalla lineas de código') 
    
    .row.justify-content-center.mb-5.align-items-center
      .col-lg-10
        .framed
          .row.justify-content-center
            .col-lg-6
              p.p-5 La condición de la relación 
                span.etiqueta (a.id_area= e.area_id) 
                | consiste en que debe estar presente en ambas tablas el valor. Cuando el empleado tiene 
                span.etiqueta NULL 
                | en 
                span.etiqueta area_id 
                | no aparece ya que no puede cumplirla. Esto se representa con un Diagrama de Venn en la conjunción porque el valor debe estar en ambas tablas.

            .col-lg-6.bg-light-blue
              figure.py-4
                img.h200(src='@/assets/curso/t5-i4.svg' alt='captura de pantalla lineas de código') 
    p.mb-5  Existe otros tipos de consultas, las 
      span.etiqueta FULL JOIN, FULL OUTER JOIN, CROSS JOIN 
      | que no se verán porque son muy poco empleadas, sin embargo, con el concepto principal se puede acceder a la documentación en la Web para comprobar su funcionamiento.
    p.mb-5  A través de la siguiente imagen se representan también otros tipos de relaciones, Diagramas de Venn que  permiten visualizar resultados retornados. Se puede usar para ayudar a comprender los resultados que se deben esperar con cada variante de las sentencias 
      span.etiqueta JOIN.
    .row.justify-content-center.mb-5
      .col-lg-8
        figure.py-4
          img(src='@/assets/curso/t5-i5.svg' alt='infografia de joins del SQL') 
        figcaption  Nota. GermanX (2017)
            
    Separador
    br
    br

    #t_5_2.titulo-segundo
      h2 5.2  Combinación externa
    p.mb-5  Es una variedad de composición de tablas que permite seleccionar algunas filas de una tabla aunque éstas no tengan correspondencia con las filas de la otra tabla con la que se combina. 
    h3.titulo-tercero
      i.fas.fa-square
      | &nbsp; LEFT JOIN
    p.mb-5  La sintaxis es muy similar a la anterior.
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img.nW(src="@/assets/curso/t5-c8.png", alt="Ejemplo de tabla")
    .row.justify-content-center.mb-5
      .col-lg-8
        p.mb-4  El resultado de este tipo de consulta contiene todos los registros de la tabla de la izquierda (la primera tabla que se define en el FROM en la consulta), independiente de si existe un registro correspondiente en la tabla de la derecha (la que se define en el JOIN).
        p.mb-4  La sentencia LEFT JOIN devuelve la pareja de todos los valores de la tabla izquierda (empleados), con los valores de la tabla de la derecha (áreas) correspondientes, si los hay, o retorna un valor nulo NULL en los campos de la tabla derecha cuando no haya correspondencia.
        p.mb-4  A diferencia del resultado presentado en el ejemplo INNER JOIN donde no se mostraba el empleado cuya área no existía, en el ejemplo que siguiente se presentarán los empleados con su respectiva área, y adicionalmente se presentará un empleado cuya area no existe.
        p.mb-4  El empleado que no tiene área se encuentra en la región amarilla del diagrama de la derecha, mientras que los empleados con área están en la franja naranja, en la intersección de empleados y áreas.

      .col-lg-4
        figure
          img(src='@/assets/curso/t5-i6.svg' alt='infografia de joins del SQL')         
    .row.justify-content-center.mb-5
      .col-lg-5
        figure
          img.nW(src='@/assets/curso/t5-i7.svg' alt='infografia de joins del SQL') 
      .col-lg-5
        figure
          img.shadow-box(src='@/assets/curso/t5-i10.jpg' alt='infografia de joins del SQL')     

    h3.titulo-tercero
      i.fas.fa-square.color-acento-botones
      | &nbsp; RIGTH JOIN
    p.mb-5  La sentencia RIGHT JOIN retorna todos los valores de la tabla derecha (áreas) con los valores de la tabla de la izquierda (empleados) correspondientes, si existen, o retorna un valor nulo NULL para los campos de la tabla izquierda cuando no haya correspondencia.
    .row.justify-content-center.mb-5
      .col-lg-8
        .tarjeta--gris.p-4
          figure
            img.nW(src="@/assets/curso/t5-c9.png", alt="Ejemplo de tabla")
    p.mb-5  En el diagrama las áreas que no tienen empleados están en el área verde mientras que las áreas con empleados están en el área anaranjada, en la intersección de empleados y áreas.
    .row.justify-content-center.mb-5
      .col-lg-5
        figure
          img.nW(src='@/assets/curso/t5-i8.svg' alt='infografia de joins del SQL') 
      .col-lg-5
        figure
          img.shadow-box(src='@/assets/curso/t5-11.jpg' alt='infografia de joins del SQL')     



</template>

<script>
export default {
  name: 'Tema5',
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
.h200{max-height: 200px}
.tabla-b__header{background-color: #FFCA28}
</style>
