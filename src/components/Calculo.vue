<script setup>
    const calcular = () => {
    const n1 = parseFloat(document.getElementById('n1').value);
    const n2 = parseFloat(document.getElementById('n2').value);
    const operacao = document.getElementById('operacao').value;
    const res = document.getElementById('res');

    let resultado;
    switch (operacao) {
    case '+':
        resultado = n1 + n2;
        break;
    case '-': 
        resultado = n1 - n2;
        break;
    case '*': 
        resultado = n1 * n2;
        break;
    case '/': 
        resultado = n1 / n2;
        break;
    }
    res.innerHTML = `O número ${n1} ${operacao} ${n2} é: ${resultado}`
}
</script>

<template>
    <form @submit.prevent="calcular">
        <input id="n1" class="form-control mb-3" type="number" placeholder="Digite o número">
        <input id="n2" class="form-control mb-4" type="number" placeholder="Digite o número">
        <select id="operacao" class="btn btn-dark ">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
        </select>
        <button type="submit" class="btn btn-primary ms-5">Calcular</button>
    </form>

    <p id="res" class="text-center mt-5"></p>
</template>