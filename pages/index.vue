<template>
  <div class="home">
    <h1 class="home-header">Got Drive?</h1>
    <img class="home-animation" :src="mazda">
  </div>
</template>

<script>
import mazda from '../static/mazda/mazda.png'
export default {
  data() {
    return {
      mazda: mazda
    }
  }
}
</script>

<style lang="scss" scoped>
  .home {
    padding-top: 5rem;
    position: relative;
  }

  .home-header {
    font-size: 4rem;
    position: absolute;
    top: 50%;
    left: 40rem;
    text-transform: uppercase;
    cursor: pointer;
    transform: translateY(-50%);
    animation: text 3s ease-in-out;
  }

  .home-header::after {
    content: "";
    display: block;
    width: 0;
    height: 3px;
    background: #000;
    transition: width 300ms ease-in-out;
  }

  .home-header:hover::after {
    width: 100%;
  }

  .home-animation {
    animation: drive 1s ease-in-out;
    transition: transform 300ms ease-in-out;
  }

  .home-animation:hover {
    transform: scale(1.1);
  }

  @keyframes drive {
    from {
      transform: translateX(60rem);
    }
    to {
      transform: translateX(0);
    }
  }

  @keyframes text {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
</style>
