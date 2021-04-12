<template>
  <div class="Card" :style="{ background: color }">
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
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    title: String,
    paragraph: String,
    color: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .Card {
    width: 300px;
    height: 100%;
    padding: 45px 60px 45px 45px;
    z-index: 2;
  }
  h1 {
    font-family: 'Big Shoulders Display', cursive;
    font-weight: 700;
    color: #fff;
    margin: 35px 0;
    font-size: 40px;
  }
  p {
    line-height: 25px;
  }
</style>
