<template>
  <div class="app-error">
    <div class="text">Error {{error.statusCode}} -  {{error.message}}</div>
    <button
      class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 border border-blue-700 rounded"
    >
      <NuxtLink to="/">Back to Home</NuxtLink>
    </button>
  </div>
</template>

<script setup>
defineProps(['error'])
</script>

<style lang="scss" scoped>
  .app-error {
    padding: 10px 100px;
    text-align: center;
    .text {
      font-size: 24px;
      color: red;
      margin-bottom: 20px;
    }
  }
</style>