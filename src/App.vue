<script setup>
import Header from './components/Header.vue';
import Calculator from './components/Calculator.vue';
import { reactive } from 'vue';

const estado = reactive({
  numA: null,
  numB: null,
  sign: '',
  resultado: null,
})

const verificaCalc = function() {
  return typeof estado.numA === 'number' && typeof estado.numB === 'number' 
}

const calcular = function() {
  const {sign} = estado;
  

  switch (sign) {
    case '+':
      return estado.resultado = estado.numA + estado.numB;
    case '-':
      return estado.resultado = estado.numA - estado.numB;
    case '*':
    return estado.resultado = estado.numA * estado.numB;
    case '/':
    return estado.resultado = estado.numA / estado.numB;
  }
}

</script>

<template>
  <Header></Header>
  <Calculator 
    :num-a="estado.numA"
    :num-b="estado.numB"
    :sign="estado.sign"
    :calcular="calcular()"
    :num-a-input="e => estado.numA = parseFloat(e.target.value)"
    :sign-change="e => estado.sign = e.target.value"
    :num-b-input="e => estado.numB = parseFloat(e.target.value)"
    :verifica-calc="verificaCalc() && !isNaN(calcular())"
  ></Calculator>
</template>

<style scoped>

</style>
