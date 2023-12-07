<script setup>
    const props = defineProps(['operacao', 'estado'])
</script>

<template>
    <section class="resultado text-center mt-4">
        <div class="container">
            <div class="resultado_content">
                <h2 v-if="estado.operacao === 'adicao'">RESULTADO:</h2>
                <h2 v-else-if="estado.operacao === 'subtracao'">DIFERENÇA:</h2>
                <h2 v-else-if="estado.operacao === 'multiplicacao'">PRODUTO:</h2>
                <h2 v-else-if="estado.operacao === 'divisao'">QUOCIENTE:</h2>
                <h2 v-else-if="estado.operacao === 'modulo'">RESTO:</h2>
                <h2 v-else-if="estado.operacao === 'exponenciacao'">VALOR EXPONENCIAL:</h2>
                
                <span class="resultadoValor">{{ operacao }}</span>
            </div>
        </div>
    </section>
</template>

<style scoped>
.resultadoValor {
    font-weight: bold;
    font-size: 32px;
}
</style>