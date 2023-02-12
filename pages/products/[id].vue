<template>
  <div class="product">
    <div class="product__title">{{product.title}}</div>
    <img
      class="product__image"
      :src="product.images[0]"
    />
    <div class="product__description">{{product.description}}.</div>
    <div class="product__price">Price: {{product.price}} dollars</div>
    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
      <NuxtLink to="/products">to Products</NuxtLink>
    </button>
  </div>
</template>

<script setup>
  const { id } = useRoute().params
  const { data: product } = await useFetch(`https://api.escuelajs.co/api/v1/products/${id}`)
  definePageMeta( {
    layout: 'navbar'
  })
</script>

<style lang="scss">
.product {
  margin: 30px auto;
  width: 500px;
  @media screen and (max-width: 768px){
    width: 300px;
  }
  &__title {
    font-size: 28px;
    text-align: center;
  }
  &__image {
    max-width: 500px;
    border-radius: 7px;
    @media screen and (max-width: 768px){
      width: 300px;
    }
  }
  &__description {
    font-size: 22px;
    text-align: justify;
  }
  &__price {
    font-weight: 700;
    font-size: 22px;
    text-align: right;
  }
}
</style>