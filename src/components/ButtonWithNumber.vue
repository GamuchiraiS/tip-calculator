<script setup>
const { number } = defineProps(['number']);
const emit = defineEmits();

const handleClick = () => {
  // Emit the value to the parent component
  emit('update:modelValue', number);
};

</script>
<template>
  <button :value="number" @click="handleClick">
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

  button:hover{
    background-color: hsl(172, 67%, 45%);
  }
</style>