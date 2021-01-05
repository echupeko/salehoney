<template>
  <div class="card" style="width: 18rem;">
    <h4 class="card-title">Мёд {{ card.name }}</h4>
    <div class="card-info">
      <img :src="this.$srcHoney + card.name + '.jpg'" v-bind:alt="'Мёд' + card.name">
    </div>
    <div class="card-body">
      <SliderProduct :product-list="card.products"/>
      <div class="transaction">
        <h4>{{ price }}</h4>
        <Button :title="'В корзину'"/>
      </div>

    </div>
  </div>
</template>

<script>
import Button from "@/components/Button";
import SliderProduct from "@/components/SliderProduct";

export default {
  name: "CardVertical",
  components: {SliderProduct, Button},
  props: ["card"],
  data() {
    return {
      price: '2000 Р.'
    }
  }
}
</script>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 260px;
  margin: 20px;
  background-color: rgba(255, 255, 255, 0.8);
  border-radius: 10px;
  border: 3px solid #4e4c4c;

}

.card-info {
  width: 100%;
  height: 200px;
}

.card-body {
  box-sizing: border-box;
  width: 100%;
  padding: 1.25rem;
}

img {
  width: 100%;
  height: 100%;
  border-radius: 50px 0;
}

.transaction {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  width: 100%;
}
</style>