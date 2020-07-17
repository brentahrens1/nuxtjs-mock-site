<template>
  <div class="products">
    <div class="products__grid" v-for="car in cars" :key="car.id">
      <div class="image-container">
        <img class="product-image" :src="car.img" :alt="car.title">
      </div>
      <h1 class="product__title"><nuxt-link :to="`/products/${car.id}`">{{ car.title }}</nuxt-link></h1>
    </div>
  </div>
</template>

<script>
import cars from '../../assets/data/cars.json'
export default {
  name: 'products',
  data() {
    return {
      cars: cars
    }
  }
}
</script>

<style lang="scss" scoped>
  .products {
    width: 100%;
    height: 100%;
    padding-top: 4rem;
    display: grid;
    grid-template-columns: repeat(2, minmax(400px, 1fr));
    grid-template-rows: repeat(auto, auto);
    grid-gap: 1rem;
  }

  .products__grid {
    display: flex;
    flex-direction: column;
  }

  .image-container {
    width: 90%;
    height: 90%;
    padding: 2rem;
  }

  .product-image {
    width: 100%;
    height: auto;
  }

  .product__title {
    text-align: center;
  }

  h1 a:link, h1 a:visited {
    text-decoration: none;
    color: #000;
    text-transform: uppercase;
    position: relative;
  }

  h1 a:link::after, h1 a:visited::after {
    content: "";
    display: block;
    width: 0;
    height: 100%;
    background: #000;
    position: absolute;
    top: 0;
    left: 0;
    transition: width 300ms ease-in-out, color 300ms ease-in-out;
  }

  h1 a:hover {
    color: #fff;
    z-index: 999;
  }

  h1 a:link:hover::after, h1 a:visited:hover::after {
    width: 100%;
  }
</style>
