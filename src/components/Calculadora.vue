<script setup>
    const props = defineProps(['estado'])
</script>

<template>
    <section class="calculadora">
    <form>
        <div class="container">
            <div class="form-group row d-flex justify-content-md-center mt-4 text-center">
            <div class="col col-md-auto">
                <label for="primeiroNumero" v-if="estado.operacao === 'adicao'">Insira o primeiro número</label>
                <label for="primeiroNumero" v-else-if="estado.operacao === 'subtracao'">Insira o minuendo</label>
                <label for="primeiroNumero" v-else-if="estado.operacao === 'multiplicacao'">Insira o primeiro fator</label>
                <label for="primeiroNumero" v-else-if="estado.operacao === 'divisao'">Insira o dividendo</label>
                <label for="primeiroNumero" v-else-if="estado.operacao === 'modulo'">Insira o dividendo</label>
                <label for="primeiroNumero" v-else-if="estado.operacao === 'exponenciacao'">Insira a base</label>
                <input :value="props.estado.primeiroNumeroTemp" @keyup="evento => props.estado.primeiroNumeroTemp = Number(evento.target.value)" type="number" id="primeiroNumero" class="form-control">
            </div>
            <div class="col col-md-auto">
                <label for="firstNumber">Insira a operação aritmética</label>
                <select @change="evento => props.estado.operacao = evento.target.value" class="form-select text-center bg-light">
                <option value="adicao">Adição (+)</option>
                <option value="subtracao">Subtração (-)</option>
                <option value="multiplicacao">Multiplicação (*)</option>
                <option value="divisao">Divisão (÷)</option>
                <option value="modulo">Módulo (%)</option>
                <option value="exponenciacao">Exponenciação (**)</option>
                </select>
            </div>
            <div class="col col-md-auto">
                <label for="segundoNumero" v-if="estado.operacao === 'adicao'">Insira o segundo número</label>
                <label for="segundoNumero" v-else-if="estado.operacao === 'subtracao'">Insira o subtraendo</label>
                <label for="segundoNumero" v-else-if="estado.operacao === 'multiplicacao'">Insira o segundo fator</label>
                <label for="segundoNumero" v-else-if="estado.operacao === 'divisao'">Insira o divisor</label>
                <label for="segundoNumero" v-else-if="estado.operacao === 'modulo'">Insira o divisor</label>
                <label for="segundoNumero" v-else-if="estado.operacao === 'exponenciacao'">Insira o expoente</label>
                <input :value="props.estado.segundoNumeroTemp" @keyup="evento => props.estado.segundoNumeroTemp = Number(evento.target.value)" type="number" id="segundoNumero" class="form-control">
            </div>
            </div>
        </div>
        </form>
    </section>
</template>