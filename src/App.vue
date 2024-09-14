<script setup>
  import { ref } from 'vue';

  const firstNumber = ref(0);
  const secondNumber = ref(0);
  const operator = ref('+');
  const result = ref(0);

  const calculate = (e) => {
    e.preventDefault()
    switch (operator.value){
      case '+':
        result.value = firstNumber.value + secondNumber.value;
        break;
      case '-':
        result.value = firstNumber.value - secondNumber.value;
        break;
      case 'X':
        result.value = firstNumber.value * secondNumber.value;
        break;
      case '/':
        result.value = firstNumber.value / secondNumber.value;
        break;
    }
  }
</script>

<template>
  <header>
    <h1>Calculadora aritmética</h1>
    <p>Faça seus calculos ultilizando operadores</p>
  </header>
  <div class="container">
    <h4>Insira dois números e selecione a operação desejada.</h4>
    <div class="container__input">
      <input type="number" v-model="firstNumber" class="first__number">
      <select v-model="operator" class="container__select">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="X">X</option>
        <option value="/">/</option>
      </select>
      <input type="number" v-model="secondNumber" class="sec__number">
      <br>
      <button @click="calculate">Calcular</button>
      <p class="result">O resultado do seu cálculo é: {{ result }}</p>
    </div>
  </div>
</template>

<style src="./styles/main.scss"></style>
