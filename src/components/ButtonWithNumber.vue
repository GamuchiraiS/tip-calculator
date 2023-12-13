<script setup>
defineProps({
  number: String,
})

function getTipPercentage(event){
  const tipPercentage = event.target.value
  console.log(tipPercentage)
}

</script>
<template>
  <button :value="number" @click="getTipPercentage">
    {{ number }}
  </button>
</template>
<style scoped>
  button{
    background-color: hsl(183, 100%, 15%);
    color: white;
    border: none;
    padding: 0.6em 1.8em;
    border-radius: 5px;
    cursor: pointer;
  }
</style>