<script setup>
import Formulario from "./components/Formulario.vue";
import useClima from "./Composables/UseClima.js";
import Clima from "./components/Clima.vue";
import Alerta from "./components/Alerta.vue";
import Spinner from "./components/Spinner.vue";

const { obtenerClima, clima, mostrarClima, cargando, error } = useClima();

</script>

<template>
  <h1 class="titulo">Buscador de clima</h1>

  <div class="contenedor buscador-clima">
    <formulario @obtener-clima="obtenerClima" />

    <spinner v-if="cargando" />
    <alerta v-if="error">{{ error }}</alerta>
    <clima v-if="mostrarClima" :clima="clima" />
  </div>
</template>
