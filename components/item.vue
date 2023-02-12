<template>
  <div class="item">
    <img
      class="item__image"
      :src="image"
    />
    <div class="item__title">{{title}}</div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  image: String,
})
</script>

<style scoped lang="scss">
.item {
  display: flex;
  flex-direction: column;
  &__image {
    width: 350px;
    margin: auto;
    border-radius: 10px;
    transition: .5s all ease;
    @media screen and (max-width: 768px){
      width: 230px;
    }
    &:hover {
      box-shadow: 0 0 10px red;
      cursor: pointer;
    }
  }
  &__title {
    font-size: 24px;
  }
}
</style>