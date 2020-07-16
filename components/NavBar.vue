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
        <div class="hamburger">
            <div class="line line-1"></div>
            <div class="line line-2"></div>
            <div class="line line-3"></div>
        </div>
        <div class="overlay">
            <div class="close">X</div>
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
    
}
</script>

<style lang="scss" scoped>
    .nav {
        width: 100%;
        height: 4rem;
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
            width: 15%;
            display: flex;
            flex-direction: row;
            justify-content: flex-end;
            list-style: none;
        }
        &__list--item {
            
            a {
                text-decoration: none;
                color: lightcyan;
                margin-right: 1rem;
            }
        }
    }

    .hamburger {
        width: 0;
        opacity: 0;
        visibility: hidden;
        height: 40px;
        margin-right: 1rem;
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        cursor: pointer;
        transition: width 300ms ease-in-out, opacity 700ms ease-in-out;

        .line {
            width: 35px;
            height: 4px;
            background: darkorchid;
            margin: 0 auto;
        }
    }

    .overlay {
        position: fixed;
        width: 100%;
        height: 100vh;
        background: lightskyblue;
        top: 0;
        left: 0;
        font-size: 3rem;
        
        &__list {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .close {
            position: absolute;
            top: 0;
            right: 1rem;
            color: #000;
            font-size: 2rem;
        }
    }

    @media (max-width: 900px) {
        .hamburger {
            width: 40px;
            opacity: 1;
            visibility: visible;
        }
    }
</style>