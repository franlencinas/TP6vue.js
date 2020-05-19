<template>
  <b-container class="mt-5 tarjeta">
    <b-row>
      <b-col>
        <img
          :src="'/images/' + instrumentoEncontrado.imagen"
          width="40%"
        />
        <p>Descripción: {{ instrumentoEncontrado.descripcion }}</p>
      </b-col>
      <b-col>
        <b-row>
          <h6>{{ instrumentoEncontrado.cantidadVendida }} vendidos</h6>
        </b-row>
        <b-row>
          <h1>{{ instrumentoEncontrado.instrumento }}</h1>
        </b-row>
        <b-row>
          <h2>$ {{ instrumentoEncontrado.precio }}</h2>
        </b-row>
        <b-row>
          <h4>Marca: {{ instrumentoEncontrado.marca }}</h4>
        </b-row>
        <b-row>
          <h4>Modelo: {{ instrumentoEncontrado.modelo }}</h4>
        </b-row>
        <b-row>
          <div v-if="instrumentoEncontrado.costoEnvio == 'G'">
            <img :src="'/images/camion.png'" width="12%" class="mb-1" />
            <span class="envioGratis">Envío gratis a todo el país</span>
          </div>
          <div v-else>
            <h4 class="envioPago">
              Costo de Envio Interior de Argentina: ${{
                instrumentoEncontrado.costoEnvio
              }}
            </h4>
          </div>
        </b-row>
        <b-row>
          <b-button href="/" variant="outline-primary"
            >Agregar al carrito</b-button
          >
        </b-row>
      </b-col>
    </b-row>
  </b-container>
</template>
<style>
.envioGratis {
  color: orange;
}

.envioPago {
  color: green;
}
.tarjeta {
  background-color: white;
  border-radius: 20px;
}
</style>
<script>
export default {
  name: "DetalleInstrumento",
  components: {},
  mounted() {
    this.getInstrumentoXId();
  },
  data() {
    return {
      instrumentoEncontrado: []
    };
  },
  methods: {
    async getInstrumentoXId() {
      const parametroId = this.$route.params.id;
      const res = await fetch("/instrumentos.json");
      const resJson = await res.json();
      this.instrumentoEncontrado = await resJson.instrumentos.find(
        instrumento => instrumento.id === parametroId
      );
    }
  }
};
</script>
