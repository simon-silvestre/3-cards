<template>
  <div class="Card" :class="{ sedan : title == 'SEDANS', suvs: title == 'SUVS', luxury: title == 'LUXURY'}" :style="{ background: color }">
    <div v-if="title == 'SEDANS'" class="image">
      <img src="@/assets/icon-sedans.svg" alt="logo voiture">
    </div>
    <div v-else-if="title == 'SUVS'" class="image">
      <img src="@/assets/icon-suvs.svg" alt="logo voiture">
    </div>
    <div v-else class="image">
      <img src="@/assets/icon-luxury.svg" alt="logo voiture">
    </div>
    <h1>{{ title }}</h1>
    <p>{{ paragraph }}</p>
    <button :style="{ color: color }">Learn More</button>
  </div>
</template>

<script>
import { gsap } from 'gsap'
export default {
  name: 'Card',
  props: {
    title: String,
    paragraph: String,
    color: String
  },
  mounted() {
    if (window.matchMedia("(min-width: 900px)").matches) {
      gsap.to('.sedan', {y: 0, duration: 2, ease: "Expo.easeInOut", delay: .8})
      gsap.to('.suvs', {y: 0, duration: 2, ease: "Expo.easeInOut", delay: 1.2})
      gsap.to('.luxury', {y: 0, duration: 2, ease: "Expo.easeInOut", delay: 1.5})
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .Card {
    position: relative;
    width: 300px;
    height: 100%;
    padding: 45px 60px 45px 45px;
    transform: translateY(-100vh);
  }
  h1 {
    font-family: 'Big Shoulders Display', cursive;
    font-weight: 700;
    color: #fff;
    margin: 30px 0;
    font-size: 40px;
  }
  p {
    line-height: 25px;
    width: 210px;
  }
  button {
    font-weight: bold;
    position: absolute;
    width: 145px;
    height: 48px;
    border-radius: 50px;
    border: 2px solid hsl(0, 0%, 95%);
    bottom: 45px;
    font-size: 15px;
    cursor: pointer;
    background: hsl(0, 0%, 95%);
    transition: 0.5s ease;

    &:hover {
      background: transparent;
      color: hsl(0, 0%, 95%)!important;
      border: 2px solid hsl(0, 0%, 95%);
    }
  }

  @media screen and (max-width: 900px) {
    .Card {
      height: 445px;
       transform: translateY(0);
    }
    p {
      width: 225px;
    }
  }
</style>
