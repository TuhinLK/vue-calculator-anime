<template>
  <div class="calculator">
    <form @submit.prevent="calculate">
      <input type="number" v-model="num1" placeholder="Number 1">
      <input type="text" v-model="operator" placeholder="Operator (+, -, *, /)">
      <input type="number" v-model="num2" placeholder="Number 2">
      <button>Calculate</button>
    </form>
    <p v-if="result >= 0">Result: {{ result }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const num1 = ref(null);
const num2 = ref(null);
const operator = ref('');
const result = ref(null);

const calculate = () => {
  switch (operator.value) {
    case '+':
      result.value = num1.value + num2.value;
      break;
    case '-':
      result.value = num1.value - num2.value;
      console.log(result.value);
      break;
    case '*':
      result.value = num1.value * num2.value;
      break;
    case '/':
      result.value = num1.value / num2.value;
      break;
    default:
      result.value = 'Invalid Operator';
  }
};
</script>
