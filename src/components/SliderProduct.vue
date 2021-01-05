<template>
  <div class="slider-bar">
    <div class="slide-point"></div>
    <div class="slide-item"
        v-for="product in visibleProduct"
        :key="product.id"
    >
      {{ product.count }} л.
    </div>
  </div>
</template>

<script>
export default {
  name: "SliderProduct",
  props: ["productList"],
  computed: {
    visibleProduct() {
      return this.productList.filter(item => item.visibile)
    }
  }
}
</script>

<style scoped>
.slider-bar {
  position: relative;
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
  z-index: 0;
}

.slide-item {
  background-color: transparent;
  z-index: 1;
  width: 25%;
  text-align: center;
  cursor: pointer;
}
</style>