<template>
    <div class="product">
        <h1>{{ car.title }}</h1>

        <nuxt-link to="/products">Back to Products</nuxt-link>
    </div>
</template>

<script>
import car from '../../assets/data/cars.json'
export default {
    data() {
        return {
            car: car
        }
    }
}
</script>

<style lang="scss" scoped>
    .product {
        padding-top: 4rem;
        width: 100%;
        height: 100%;
    }
</style>