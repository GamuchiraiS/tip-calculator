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

  .tile > p{
    color: hsl(172, 67%, 45%);
    font-size: 1.5em;
  }

  .text{
    display: flex;
    flex-direction: column;
  }

  .text p:first-child{
    color: #ffffff;
  }

  .text p:not(:first-child){
    color: hsl(184, 14%, 56%);
    font-size: 0.8em;
  }

</style>