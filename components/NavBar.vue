<template>
    <div class="nav">
        <div class="nav__logo">
            <nuxt-link to="/">Home</nuxt-link>
        </div>
        <ul class="nav__list">
            <li class="nav__list--item">
                 <nuxt-link to="/about">About</nuxt-link>
                 <nuxt-link to="/products">Products</nuxt-link>
            </li>
        </ul>
        <div class="hamburger" :class="{'opened': open}" @click="open = !open">
            <div class="hamburger__bars">
                <div class="hamburger__bar bar-1"></div>
                <div class="hamburger__bar bar-2"></div>
                <div class="hamburger__bar bar-3"></div>
            </div>
        </div>
        <div :class="[open ? 'overlay-open' : 'overlay-closed']">
            <ul class="overlay__list">
                <li class="overlay__list--item">
                    <nuxt-link to="/about">About</nuxt-link>
                    <nuxt-link to="/products">Products</nuxt-link>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            open: false
        }
    }
}
</script>

<style lang="scss" scoped>

    @mixin overlay($left) {
        position: fixed;
        width: 100%;
        height: 100vh;
        background: lightskyblue;
        top: 0;
        left: $left;
        font-size: 3rem;
        transition: left 800ms ease-in-out;
    }

    @mixin hamburger {
        display: none;
        width: 45px;
        height: 40px;
        position: relative;
        top: 0;
        right: 1rem;
        z-index: 999;
        cursor: pointer;
    }

    .nav {
        width: 100%;
        height: 4rem;
        position: fixed;
        top: 0;
        right: 0;
        background: lightcoral;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        color: lightcyan;

        &__logo {
            font-size: 1.5rem;
            margin-left: 1rem;

            a:link, a:visited {
                text-decoration: none;
                list-style: none;
                color: lightcyan;
            }
        }

        &__list {
            width: 25%;
            display: flex;
            flex-direction: row;
            justify-content: flex-end;
            list-style: none;
        }
        &__list--item {
            
            a:link, a:visited {
                text-decoration: none;
                color: lightcyan;
                margin-right: 1rem;
            }
        }
    }

    .hamburger {
        display: none;
        width: 45px;
        height: 40px;
        position: relative;
        top: 0;
        right: 1rem;
        z-index: 999;
        cursor: pointer;

        &__bars {
            width: 100%;
            height: 100%;
            padding: .5rem 0;
            display: flex;
            flex-direction: column;
            justify-content: space-around;
            align-items: center;
        }

        &__bar {
            width: 35px;
            height: 4px;
            background: darkorchid;
            opacity: 1;
            transform: rotate(0) translateY(0) translateX(0);
            transform-origin: 1em 1em;
            transition: transform 0.3s ease-in-out, opacity 0.2s ease-in-out;
        }
    }
    
    .opened .bar-1 {
        transform: rotate(45deg) translateY(0) translateX(0);
    }

    .opened .bar-2 {
        opacity: 0;
    }

    .opened .bar-3 {
        transform: rotate(-45deg) translateY(0em) translateX(0em);
        margin-bottom: 1.3em;
        margin-left: 2.6em;
    }

    .overlay-open {
        @include overlay(0);
    }

    .overlay-closed {
        @include overlay(100rem);
    }

    .overlay__list {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    @media (max-width: 900px) {
        .hamburger {
            display: block;
        }

        .nav__list {
            display: none;
        }
    }
</style>