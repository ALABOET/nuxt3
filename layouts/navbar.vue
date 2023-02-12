<template>
  <div class="app-navbar">
    <ul class="list">
      <li><NuxtLink to="/">Home</NuxtLink></li>
      <li><NuxtLink to="/about">About</NuxtLink></li>
      <li><NuxtLink to="/products">Products</NuxtLink></li>
    </ul>
  </div>
  <slot />
</template>

<script setup>
</script>

<style scoped lang="scss">
.app-navbar {
  width: 300px;
  border: 1px solid green;
  border-radius: 5px;
  margin: 10px auto;
  .list {
    padding: 10px 20px;
    display: flex;
    list-style-type: none;
    justify-content: space-between;
    li {
      text-decoration: none;
      font-size: 20px;
      transition: .5s all ease;
      &:hover {
        cursor: pointer;
        color: blue;
      }
    }
  }
}
</style>