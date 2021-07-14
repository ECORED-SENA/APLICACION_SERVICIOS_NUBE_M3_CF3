<template lang="pug">
.curso-main-container.pb-3
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5
    .titulo-principal
      .titulo-principal__numero
        span  3
      h1 Interface de Línea de Comandos de MySQL

    //-- Aqui viene el banner

    p.mb-5  Se creará una tabla con la que seguiremos <b>ejemplificando la sintaxis del SQL.</b>

    #t_3_1.titulo-segundo
      h2 3.1  Inserción de registros
    p.mb-5  La forma más directa de implantar una fila nueva en una tabla es por medio de una sentencia INSERT. De la manera más sencilla de esta sentencia se debe indicar la tabla a la que se quiere agregar filas, y los valores de cada columna. Las columnas de tipo cadena o fechas tienen que estar entre comillas sencillas o dobles,  esto no es obligatorio para las columnas numéricas, aunque también pueden estar entrecomilladas.




















    Separador
    br
    br  
    #t_3_2.titulo-segundo
      h2 3.2  Edición de registros
    p.mb-5  Tenemos la posibilidad de cambiar valores de las filas de una tabla utilizando la sentencia UPDATE. En su manera más fácil, los cambios se usan a cada una de las filas, y a las columnas que se les especifique.






    Separador
    br
    br  
    #t_3_3.titulo-segundo
      h2 3.3 Borrado de registros
    p.mb-5  Para borrar filas se utiliza la sentencia 
      span.etiqueta DELETE. 
      | La sintaxis es muy similar a la de 
      span.etiqueta UPDATE:








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

<style lang="sass" scoped></style>
