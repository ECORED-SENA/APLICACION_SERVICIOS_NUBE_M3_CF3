<template lang="pug">
.curso-main-container.introduccion
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5.mb-5
  
    .titulo-principal
      .titulo-principal__numero
        span
          i.fas.fa-info
      h1 Introducción
    
    figure.mb-5
      img(src="@/assets/curso/t0-i1.jpg", alt="Imagen decorativa relacionada con codigos y bases de datos")
    .row
      .col-lg-3
        figure.mb-5
          img(src="@/assets/curso/t0-i2.svg", alt="logotipo de MySQL")
      .col-lg-9
        p.mb-3  Las siglas <b>SQL,</b> vienen del inglés <b>Structured Query Language,</b> es un lenguaje estándar que permite manipular los datos de una base de datos relacional. Casi todos los Sistemas de Gestión de Bases de Datos Relacionales (SGBD) implementan este lenguaje y mediante él se realizan todo tipo de actividad en la base de datos. En este punto se hace una presentación del <b>lenguaje SQL,</b> enfocándose en las sentencias de consulta de datos, empleando la interfaz de consola de línea de comandos con el fin de fortalecer las técnicas de administración remota. <b>Finalmente se presentará la interfaz de administración grafica para hacer las mismas operaciones.</b>

</template>

<script>
export default {
  name: 'Introduccion',
  data: () => ({
    // variables de vue
  }),
}
</script>

<style lang="sass" scoped>
.introduccion
</style>
