<template>
  <div class="basket-block">
    <img src="/resource/basket.png" @click="bask">
  </div>
</template>

<script>
export default {
  name: "Basket",
  methods: {
    bask() {
      console.log(this.$basketArray)
    }
  }
}
</script>

<style scoped>
.basket-block {
  cursor: pointer;
}

img {
  width: 60px;
  height: 60px;
  margin-right: 20px;
}
</style>