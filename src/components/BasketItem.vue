<template>
  <div class="item">
    <h3 class="item-title">Мёд {{ honey.honey.name + ' ' + honey.pack.count }} л. </h3>
    <div class="counter">
      <input type="submit" value="-">
      <input type="number" step="1" min="1" max="20">
      <input type="submit" value="+">
    </div>
    <h3 class="item-price">{{ honey.pack.price }}</h3>
    <button class="remove-item"></button>
  </div>
</template>

<script>

export default {
  name: "BasketItem",
  props: ["honey"],
  data() {
    return {
      d: ''
    }
  }
}
</script>

<style scoped>
.item {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  background-color: #f2ffee;
  border: 2px solid #4e4c4c;
  border-radius: 10px;
  margin: 10px;
  width: 100%;
}

.counter {
  margin: 10px;
  background-color: white;
}

input {
  margin: 5px;
}
</style>