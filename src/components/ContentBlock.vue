<template>
  <div class="container">
    <h1>{{ navItem.title }}</h1>
    <Sale
        v-if="navItem.id == 1"
        :card="createCard"
    />
    <Catalog v-if="navItem.id == 2"/>
  </div>
</template>

<script>
import Sale from "@/components/Sale";
import Catalog from "@/components/Catalog";

export default {
  name: "ContentBlock",
  components: {Catalog, Sale},
  props: ["navItem"],
  data() {
    return {
      idSaleHoney: [1, 1]
    }
  },
  computed: {
    createCard() {
      let typeHoney = this.$catalogList[this.idSaleHoney[0]];
      let versionProduct = typeHoney.products[this.idSaleHoney[1]];
      let card = {
        id: typeHoney.id,
        title: typeHoney.name,
        description: typeHoney.description,
        count: versionProduct.count,
        price: versionProduct.price,
        salePrice: versionProduct.salePrice
      };
      return card;
    }
  }
}
</script>

<style scoped>
.container {
  width: 100%;
}

h1 {
  margin: 25px 0;
  background-color: rgba(255, 255, 255, 0.5);
  width: 100%;
  height: 50px;
  text-align: center;
  line-height: 50px;
}
</style>