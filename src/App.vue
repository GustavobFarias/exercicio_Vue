<script setup>
import cabecalho from './components/Cabecalho.vue';
import calculo from './components/Calculo.vue';
</script>

<template>
  <div class="container">
    <cabecalho />
    <calculo />
  </div>
</template>

<style scoped>
.container {
    max-width: 500px;
    margin: auto;
  }
</style>
