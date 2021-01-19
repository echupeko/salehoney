<template>
  <div class="basket-block">
    <img src="/resource/basket.png" @click="openBasket">
    <BasketForm v-if="visibleBasket"/>
  </div>
</template>

<script>
import BasketForm from "@/components/BasketForm";
export default {
  name: "Basket",
  data() {
    return{
      visibleBasket: false
    }
  },
  components: {BasketForm},
  methods: {
    openBasket() {
      this.visibleBasket = !this.visibleBasket;
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