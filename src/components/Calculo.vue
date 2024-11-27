<script setup>
import { ref, watch} from 'vue';

const n1 = ref(0);
const n2 = ref(0);
const operacao = ref('+');
const resultado = ref('');

const calcular = () => {

    let res;
    switch (operacao.value) {
    case '+':
        res = n1.value + n2.value;
        break;
    case '-': 
        res = n1.value - n2.value;
        break;
    case '*': 
        res = n1.value * n2.value;
        break;
    case '/': 
        res =  n2.value !== 0 ? n1.value / n2.value : 'Erro: Divisão por zero';
        break;
    default:
        res = 'Operação inválida'
    }
    resultado.value = res;
}

watch([n1, n2, operacao], calcular)
</script>

<template>
    <form class="d-flex align-items-center">
        <input v-model="n1" class="form-control mm-2" type="number" placeholder="0">
        <select v-model="operacao" class="form-control text-center m-2">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
        </select>
        <input v-model="n2" class="form-control m-2" type="number" placeholder="0">
    </form>
    <p class="text-center fw-bold fs-2 mt-4">Resultado:</p>
    <p class="fw-bold fs-3 text-center mt-1">{{ resultado }}</p>
</template>