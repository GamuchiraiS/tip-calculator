<script setup>
defineProps({
  heading: String,
  subtext: String,
  number: Number
})
</script>
<template>
  <div class="tile">
    <div class="text">
      <p> {{ heading }}</p>
      <p> {{ subtext }}</p>
    </div>
    <p> $ {{ number }}</p>
  </div>
</template>
<style scoped>

  .tile{
    display: flex;
    justify-content: space-between;
  }

  .text{
    display: flex;
    flex-direction: column;
  }

</style>