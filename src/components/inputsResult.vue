<script setup>
    const props = defineProps(['estado', 'mudaTamanho1', 'mudaTamanho2'])
</script>

<template>
    <div class="input-div">
        <input @keyup="evento => props.estado.input1 = evento.target.value" :style="props.mudaTamanho1" type="number" class="input-num" placeholder="000">
        <input disabled :value="props.estado.operationIcon" class="operation-icon">
        <input @keyup="evento => props.estado.input2 = evento.target.value" :style="props.mudaTamanho2" type="number" class="input-num" placeholder="000">
      </div>
      <div class="result">
        <input disabled :value="props.estado.result" class="result-input">
      </div>
</template>

<style>

.input-div, .result{
  background-color: rgb(33, 33, 33);
}

.input-div{
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-end;
  color:aliceblue;
  max-width: 100%;
  padding: 20px;
  border-top-left-radius: 15px;
  border-top-right-radius: 15px;
}

.input-num{
  text-align: right;
  color: aliceblue;
  background-color: transparent;
  font-size: 2em;
  border: none;
  border-bottom: 1px solid rgb(184, 184, 184);
  width: 3ch;
}
.operation-icon{
  background-color: transparent;
  border: none;
  width: 1em;
  font-size: 1.5em;
  text-align: center;
  color: #e6e6e6;
}

.result{
  color: rgb(227, 152, 4);
  text-align: end;
  max-width: 100%;
  padding: 10px;
}
.result-input{
  font-size: 2em;
  background-color: transparent;
  border: none;
  color: chocolate;
  text-align: right;
}

@media(max-width: 425px){
    .result{
        padding: 0px;
    }
    .result-input{
        font-size: 1.8em;
    }
}

</style>