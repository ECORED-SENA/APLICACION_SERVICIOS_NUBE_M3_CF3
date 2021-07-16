<template lang="pug">
.curso-main-container.pb-3
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5
    .titulo-principal
      .titulo-principal__numero
        span  5
      h1 Consulta multitablas - DML
    .row.justify-content-center.mb-5
      .col-lg-10
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
            img.nW(src="@/assets/curso/t5-c1.svg", alt="Ejemplo de tabla")
    p.mb-5  Se insertarán los siguientes datos:
    .row.justify-content-center.mb-3
      .col-lg-10
        .tarjeta--gris.p-4
          pre
            code INSERT INTO areas (id_area, area) VALUES ('17', 'Ventas'), ('19', 'Producción'),<br>  ('20', 'Ingeniería') ('21', 'Mercadeo');
    .row.justify-content-center.mb-3
      .col-lg-10
        .tarjeta--gris.p-4
          figure.mb-5
            img.nW(src="@/assets/curso/t5-c3.svg", alt="Ejemplo de tabla")
    .row.justify-content-center.mb-5
      .col-lg-10
        .tarjeta--gris.p-4
          figure.mb-5
            img.nW(src="@/assets/curso/t5-c4.svg", alt="Ejemplo de tabla")            
    
    p.mb-5  Los datos quedan así:
    .row.justify-content-center.mb-5
      .col-lg-5
        .tabla-b__header  Empleados
        .tarjeta--gris.p-4
          figure
            img.nW(src="@/assets/curso/t5-c5.svg", alt="Ejemplo de tabla") 
      .col-lg-5
        .tabla-b__header  Áreas
        .tarjeta--gris.p-4
          figure
            img.nW.mb-5(src="@/assets/curso/t5-c6.svg", alt="Ejemplo de tabla") 


    #t_5_1.titulo-segundo
      h2 5.1  Combinación interna (INNER JOIN)
    .row.mb-4
      .col-lg-3
        figure
          img(src='@/assets/curso/t5-i2.svg' alt='imagen decorativa') 
      .col-lg-9
        p.mb-5  Con esta operación, cada fila en la tabla empleados es combinada (o unida) con los correspondientes de la tabla areas que satisface la condición que se especifiquen en el predicado del JOIN. Cualquier fila de la tabla empleados o de la tabla areas que no tenga uno correspondiente en la otra tabla (areas) es excluido y solo aparecerán los que tengan correspondencia en la otra tabla. Este es el tipo de JOIN más utilizado, por lo que es considerado el tipo de combinación predeterminado. 
    .row.justify-content-center.mb-5
      .col-lg-6
        .tarjeta--gris.p-4
          pre
            code SELECT MONTH(registro) AS mes, COUNT(*) AS cantidad<br>FROM cdr<br>WHERE LENGTH(origen) &gt; 3 AND YEAR(registro) = 2017<br>GROUP BY mes
      .col-lg-5
        figure
          img.shadow-box(src='@/assets/curso/t4-i24.jpg' alt='captura de pantalla lineas de código') 




    
    Separador
    br
    br



    #t_5_2.titulo-segundo
      h2 5.2  Combinación externa.

    
    Separador
    br
    br


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

<style lang="sass" scoped></style>
