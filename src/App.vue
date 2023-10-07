<script setup>
import { reactive } from 'vue';

const estado = reactive({
  operacao: '1',
  valor1: 0,
  valor2: 0,
  resultado: 0,
})

function executaOperacao() {


    if (estado.operacao === '1') {
      estado.resultado = estado.resultado = estado.valor1 + estado.valor2;
    } else if (estado.operacao === '2') {
      estado.resultado = estado.valor1 - estado.valor2;
    } else if (estado.operacao === '3') {
      estado.resultado = estado.valor1 * estado.valor2;
    } else if (estado.operacao === '4') {
      if (estado.valor2 != 0) {
      estado.resultado = estado.valor1 / estado.valor2;
      } 
    }
}
</script>

<template>
  <div class="container">
    <h1>Operações Aritméticas</h1>

    <span>Selecione a operação </span>
    <select @change="evento => estado.operacao = evento.target.value" @click="executaOperacao()">
      <option value="1">Adição</option>
      <option value="2">Subtração</option>
      <option value="3">Multiplicação</option>
      <option value="4">Divisão</option>
    </select> <br><br>

    <span>Valor 1 </span>
    <input type="number" v-model="estado.valor1" @click="executaOperacao()" @keyup="executaOperacao()" placeholder="Digite Valor 1"> <br>
    <span>Valor 2 </span>
    <input type="number" v-model="estado.valor2" @click="executaOperacao()" @keyup="executaOperacao()" placeholder="Digite Valor 2"> <br><br>

    <p>Resultado: {{ estado.resultado }}</p> <br>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
}

.container {
  max-width: 360px;
  background-color: rgb(214, 212, 212);
  padding: 24px 24px;
}

h1 {
  padding-bottom: 24px;
}

select {
  font-size: 18px;
}

input {
  font-size: 18px;
  margin-bottom: 5px;
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
}

p {
  font-size: 30px;
  font-weight: bold;
  color: blue;
}

span {
  font-size: 14px;
  font-weight: bold;
  color: rgba(0, 0, 0, 0.74);
}
</style>
