<template>
  <div class="mt-4">
    <b-card
      :img-src="'/images/' + instrumentoParam.imagen"
      img-left
      img-width="20%"
      img-height="20%"
      class="mb-3"
    >
      <b-card-title
        :title="instrumentoParam.instrumento"
        class="titulo"
      ></b-card-title>
      <b-card-text>
        <h5 :precio="instrumentoParam.precio">
          Precio: {{ instrumentoParam.precio }}
        </h5>
        <h5 :cantidadVendida="instrumentoParam.cantidadVendida">
          Cant. Vendida: {{ instrumentoParam.cantidadVendida }}
        </h5>
        <h5 v-if="instrumentoParam.costoEnvio == 'G'" class="envioGratis">
          <img :src="'/images/camion.png'" width="4%" class="mb-1" />
          Envio gratis a todo el país
        </h5>
        <h5 v-else class="envioPago">
          Costo de Envio Interior de Argentina: ${{
            instrumentoParam.costoEnvio
          }}
        </h5>
      </b-card-text>
      <b-button
        :href="'/detalle/' + instrumentoParam.id"
        variant="primary"
        block
      >
        <b>Detalle</b>
      </b-button>
    </b-card>
  </div>
</template>
<script>
export default {
  props: ["instrumentoParam"]
};
</script>
<style>
.envioGratis {
  color: orange;
}

.envioPago {
  color: green;
}
</style>
