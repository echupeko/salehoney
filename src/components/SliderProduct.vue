<template>
  <div class="slider-bar">
    <div class="slide-point"
         :style="{width: 100/visibleProduct.length + '%', left: positionPoint}"
    ></div>
    <div class="slide-item"
         v-for="product in visibleProduct"
         :key="product.id"
         :style="{width: 100/visibleProduct.length + '%'}"
         @click="$emit('changeProduct', product, 100/visibleProduct.length);"
    >
      {{ product.count }} л.
    </div>
  </div>
</template>

<script>
export default {
  name: "SliderProduct",
  props: ["productList"],
  data() {
    return {
      positionPoint: '',
    }
  },
  computed: {
    visibleProduct() {
      let newProductList = this.productList.filter(item => item.visible);
      return newProductList
    }
  }
}
</script>

<style scoped>
.slider-bar {
  position: relative;
  display: flex;
  width: 100%;
  height: 36px;
  border-radius: 100px;
  border: 1px solid #4e4c4c;
}

.slide-point {
  position: absolute;
  border-radius: 100px;
  background-color: rgba(64, 64, 64, 0.4);
  width: 25%;
  height: 100%;
  left: 0;
  z-index: 0;
  transition: all .3s ease-in-out;
}

.slide-item {
  background-color: transparent;
  z-index: 1;
  width: 25%;
  text-align: center;
  cursor: pointer;
  justify-content: center;
  align-items: center;
  display: flex;
}
</style>