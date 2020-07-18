<template>
    <div class="product">
        <nuxt-link to="/products">Back to Products</nuxt-link>
        <h1>{{ car.title }}</h1>
        <div class="product__image">
            <img :src="car.img" :alt="car.title">
        </div>
    </div>
</template>

<script>
import cars from '../../assets/data/cars.json'
export default {
    name: 'Product',
    data() {
        return {
            id: this.$route.params.id,
            car: {}
        }
    },
    mounted() {
        this.car = cars.find(item => item.id == this.$route.params.id)
    }
}
</script>

<style lang="scss" scoped>
    .product {
        padding-top: 4rem;
        width: 100%;
        height: 100%;
    }
    
    .product__image {
        width: 50%;
    }

    .product__image img {
        width: 100%;
    }
</style>
