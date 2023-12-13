<script setup>
import {ref} from 'vue'
defineProps({
  placeholder: String,
})

const initialValue = ref('')

function getInputFieldValue(event){
  const inputFieldValue = event.target.value
  console.log(inputFieldValue)
}

</script>
<template>
  <input
      type="number"
      v-model="initialValue"
      :placeholder="placeholder"
      @change="getInputFieldValue"
  />
  <p>This is the input: {{ initialValue }}</p>
</template>
<style scoped>

</style>