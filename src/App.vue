<script setup>
import { reactive } from 'vue';
import cabecalho from './components/inputsResult.vue';
import btns from './components/btns.vue';

const estado = reactive({
  input1:0,
  input2:0,
  result: 'NaN',
  operationIcon: '?' //ícone da operação como o + ou o -, para aparecer ao meio do inputs 
})

const mudaTamanho1 = () => {
  const tamanho = estado.input1.length
  return `width:${tamanho}ch`
}
const mudaTamanho2 = () => {
  const tamanho = estado.input2.length
  return `width:${tamanho}ch`
}

</script>

<template>
    <main>
      <cabecalho :estado="estado" :muda-tamanho1="mudaTamanho1()" :muda-tamanho2="mudaTamanho2()" />
      <btns :estado="estado"/>
    </main>
</template>

<style>
*{
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
main{
  display: flex;
  flex-direction: column;
  max-width: 700px;
  width: 100%;
  margin: 0 auto;
  margin-top: 15%;
}
</style>
