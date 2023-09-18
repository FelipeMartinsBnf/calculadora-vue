<script setup>
    const props = defineProps(['estado'])
    const adicao = () => {
        props.estado.operationIcon = '+'
        return props.estado.result = (parseInt(props.estado.input1) + parseInt(props.estado.input2))
    }
    const sub = () => {
        props.estado.operationIcon = '-'
        return props.estado.result = (parseInt(props.estado.input1) - parseInt(props.estado.input2))
    }
    const mult = () => {
        props.estado.operationIcon = '*'
        return props.estado.result = (parseInt(props.estado.input1) * parseInt(props.estado.input2))
    }
    const divi = () => {
        props.estado.operationIcon = '÷'
        return props.estado.result = (parseInt(props.estado.input1) / parseInt(props.estado.input2))
    }

</script>

<template>
    <div class="operators">
        <button type="button" class="border-l" @click="adicao()">+</button>
        <button type="button" @click="sub()">-</button>
        <button type="button" @click="mult()">x</button>
        <button type="button" class="border-r" @click="divi()">%</button>
      </div>
</template>

<style>
.operators{
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  align-content: space-between;
}
button{
  cursor: pointer;
  width: 25%;
  padding: 20px;
  background-color: #e6e6e6;
  border: 1px solid #c8c8c8;
  color: chocolate;
  font-weight: bold;
}
button:hover{
  background-color: #c8c8c8;
}

.border-r{
  border-bottom-right-radius: 6px ;
}
.border-l{
  border-bottom-left-radius: 6px ;
}
</style>