<script setup>
    import Cabecalho from './components/Cabecalho.vue'
    import Calculadora from './components/Calculadora.vue'
    import Resultado from './components/Resultado.vue'
    import { getOperacao, estado } from './scripts/Script.vue'
</script>

<template>
  <Cabecalho />
  <Calculadora :estado="estado"/>
  <Resultado :estado="estado" :operacao="getOperacao()"/>
</template>

<style scoped>

</style>