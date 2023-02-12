<template>
  <div class="app-catalog">
    <div class="products-list">
      <div
        class="products-list__category"
        v-for="product in products"
        :key="product.id"
      >
        <NuxtLink :to="`/products/${product.id}`">
          <Item
            :image="product.images[0]"
            :title="product.title"
          />
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>
const { data: products } = await useFetch('https://api.escuelajs.co/api/v1/products?offset=0&limit=24')
definePageMeta( {
  layout: 'navbar'
})
</script>

<style scoped lang="scss">
.app-catalog {
  padding: 0 100px;
  @media screen and (max-width: 1000px){
    padding: 0 20px;
  }
  .products-list {
    display: flex;
    flex-wrap: wrap;
    &__category {
      margin: 20px auto;;
      flex-basis:33.333333%;
      text-align: center;
      @media screen and (max-width: 1000px){
        flex-basis: 33.333333%;
      }
      @media screen and (max-width: 768px){
        flex-basis: 50%;
      }
      @media screen and (max-width: 500px){
        flex-basis: 100%;
      }
    }
  }
}

</style>