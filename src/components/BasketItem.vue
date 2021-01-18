<template>
  <div>
    <h3 class="item-title"></h3>
    <div class="counter">
      <input type="submit" value="-">
      <input type="number" step="1" min="1" max="20">
      <input type="submit" value="+">
    </div>
    <h3 class="item-price"></h3>
    <button class="remove-item"></button>
  </div>
</template>

<script>

export default {
  name: "BasketItem",
}
</script>

<style scoped>

</style>