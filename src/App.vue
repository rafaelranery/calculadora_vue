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

const verificaCalc = () => {
  return typeof estado.numA === 'number' && typeof estado.numB === 'number' 
}

const calcular = () => {
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
  <Calculator />

  <div class="container">
    <div class="calc-div">
      <input @keyup="e => estado.numA = parseFloat(e.target.value)" class="number-input" type="number" placeholder="0">
      <select class="operation-input" @change="e => estado.sign = e.target.value">
        <option value="">
          
        </option>
        <option value="+">
          +
        </option>
        <option value="-">
          -
        </option>
        <option value="*">
          *
        </option>
        <option value="/">
          /
        </option>
      </select>
      <input @keyup="e => estado.numB = parseFloat(e.target.value)" class="number-input" type="number" placeholder="0">
    </div>
    <div class="product-div">
      <p v-if="verificaCalc() && !isNaN(calcular())" >{{ estado.numA }} {{ estado.sign}} {{ estado.numB }} = {{ calcular() }}</p>
      <!-- <p v-else-if="">São necessários dois numerais para realização da conta</p> -->
      <p v-else>Realize uma conta!  <span class="instructions-disclaimer">* São necessários dois dígitos.</span></p>
    </div>
  </div>
</template>

<style scoped>
.calc-div {
  display: flex;
  margin: 64px auto;
  max-width: fit-content;
  gap: 24px;
}

.number-input {
  max-width: 104px;
  /* height: 104px; */
  font-size: 44px;
  border-radius: 8px;
  outline: none;

}

.operation-input {
  border-radius: 50%;
  width: 88px;
  font-size: 44px;
  padding: 10px;
  text-align: center;
}

.product-div {
  text-align: center;
  width: 344px;
  margin: 0 auto;
  font-size: 64px;
}

.instructions-disclaimer {
  font-size: 14px;
  display: block;
}
</style>
