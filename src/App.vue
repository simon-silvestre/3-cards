<template>
  <div id="app">
    <div class="overlay">
      <p>Card</p>
    </div>
    <div class="cardContainer">
      <Card title="SEDANS" paragraph="Choose a sedan for its affordability and excellent fuel economy. Ideal for cruising in the city or on your next road trip." color="hsl(31, 77%, 52%)"/>
      <Card title="SUVS" paragraph="Take an SUV for its spacious interior, power, and versatility. Perfect for your next family vacation and off-road adventures." color="hsl(184, 100%, 22%)" />
      <Card title="LUXURY" paragraph="Cruise in the best car brands without the bloated prices. Enjoy the enhanced comfort of a luxury rental and arrive in style." color="hsl(179, 100%, 13%)" />
    </div>
  </div>
</template>

<script>
import Card from './components/Card.vue'
import { gsap } from 'gsap'

export default {
  name: 'App',
  components: {
    Card
  },
  mounted() {
    gsap.to('.overlay', {x: -100 + 'vw', duration: 2, ease: "Expo.easeInOut"})
  }
}
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Big+Shoulders+Display:wght@700&display=swap');
  @import url('https://fonts.googleapis.com/css2?family=Lexend+Deca&display=swap');
  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
  #app {
    font-family: 'Lexend Deca', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    font-size: 15px;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: hsl(0, 0%, 95%);
    color: hsla(0, 0%, 100%, 0.75);
  }
  .cardContainer {
    display: flex;
    width: 900px;
    height: 500px;
    border-radius: 10px;
    overflow: hidden;
  }
  .overlay {
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    top: 0;
    z-index: 99;
    background-color: hsl(184, 100%, 22%);

    p {
      font-size: 100px;
      font-weight: bold;
      text-transform: uppercase;
    }
  }

   @media screen and (max-width: 900px) {
     #app {
       height: auto;
     }
     .cardContainer {
       width: auto;
       height: auto;
       flex-direction: column;
       margin: 80px 0;
     }
  }
</style>
