<script setup>
  import { ref } from 'vue';

  /* Para deixar o atributo dinâmico e reativo, precisar usar o ref do Vue 
   * Somente para valores primitivos: números, strings, etc...
  */
  let count = ref(0);

  function increment() {
    count.value++;
  }

</script>

<template>
  <div>
    <h1>{{ count }}</h1>
    <button @click="increment()">Incrementar</button>
  </div>
</template>

<style scoped>

</style>
