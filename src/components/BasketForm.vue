<template>
  <div>
    <h3>Ваша корзина пуста</h3>
    <BasketItem
        v-for="honey in this.$basketArray"
        :honey="honey"
        :key="honey.id"
    />
  </div>
</template>

<script>
import BasketItem from "@/components/BasketItem";

export default {
  name: "BasketForm",
  components: {BasketItem}
}
</script>

<style scoped>

</style>