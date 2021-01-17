<template>
  <div class="card" style="width: 18rem;">
    <h3 class="card-title">Мёд {{ card.name }}</h3>
    <div class="card-info">
      <img :src="this.$srcHoney + card.name + '.jpg'" v-bind:alt="'Мёд' + card.name">
    </div>
    <div class="card-body">
      <SliderProduct
          :productList="card.products"
          @changePrice="changePrice"
      />
      <div class="transaction">
        <h2>{{ product.price + ' Р.' }}</h2>
        <Button class="button" :title="'В корзину'" @click="itemPushToBasket(card,product)"/>
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
      product: {}
    }
  },
  methods: {
    changePrice(product) {
      this.product = product;
    },
    itemPushToBasket(honey, pack) {
      let basketItem = {
        honey: honey,
        pack: pack
      }
      this.$basketArray.push(basketItem)

    }
  }
}
</script>

<style lang="scss" scoped>
.card {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 260px;
  margin: 20px;
  background-color: rgba(255, 255, 255, 0.8);
  border-radius: 50px 15px;
  border: 3px solid #4e4c4c;

}

.card-title {
  margin: 5px 0;
}

.card-info {
  width: 100%;
  height: 200px;
}

.card-body {
  box-sizing: border-box;
  width: 100%;
  padding: 1rem;
}

img {
  width: 100%;
  height: 100%;
  border-radius: 50px 0;
}

.transaction {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  margin-top: 15px;
}

.transaction {
  h2 {
    text-align: center;
    width: calc(100% - 100px);
  }
}
</style>