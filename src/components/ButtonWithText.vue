<script setup>
defineProps({
  text: String,
})
</script>
<template>
  <button>
    {{ text }}
  </button>
</template>
<style scoped>
  button{
    background-color: hsl(172, 67%, 45%);
    color: white;
    border: none;
    padding: 0.6em 1.8em;
    border-radius: 5px;
    cursor: pointer;
  }
</style>