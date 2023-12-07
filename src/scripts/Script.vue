<script>
    import { reactive } from 'vue';

    export const estado = reactive({
        operacao: 'adicao',
        primeiroNumeroTemp: 0,
        segundoNumeroTemp: 0,
        resultado: 0
    })

    export const operacaoAdicao = () => {
        return estado.segundoNumeroTemp + estado.primeiroNumeroTemp
    }

    export const operacaoSubtracao = () => {
        return estado.primeiroNumeroTemp - estado.segundoNumeroTemp
    }

    export const operacaoMultiplicacao = () => {
        return estado.primeiroNumeroTemp * estado.segundoNumeroTemp
    }

    export const operacaoDivisao = () => {
        if (estado.primeiroNumeroTemp === 0) {
            estado.primeiroNumeroTemp = 1
            alert('O numerador da divisão não pode ser 0')
        } else if (estado.segundoNumeroTemp === 0) {
            estado.segundoNumeroTemp = 1
            alert('O denominador da divisão não pode ser 0')
        }
        return estado.primeiroNumeroTemp / estado.segundoNumeroTemp
    }

    export const operacaoModulo = () => {
        if (estado.segundoNumeroTemp === 0) {
            estado.segundoNumeroTemp = 1
            alert('O divisor não pode ser 0')
        }
        return Math.abs(estado.primeiroNumeroTemp % estado.segundoNumeroTemp)
    }

    export const operacaoExponenciacao = () => {
        return estado.primeiroNumeroTemp ** estado.segundoNumeroTemp
    }

    export const getOperacao = () => {
        const { operacao } = estado;

        switch (operacao) {
            case 'subtracao': {
                return operacaoSubtracao();
            }
            case 'multiplicacao': {
                return operacaoMultiplicacao();
            }
            case 'divisao': {
                return operacaoDivisao();
            }
            case 'modulo': {
                return operacaoModulo();
            }
            case 'exponenciacao': {
                return operacaoExponenciacao()
            }
            default:
                return operacaoAdicao()
        }
    }
</script>