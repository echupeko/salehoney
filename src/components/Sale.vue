<template>
  <div class="sale-block">
    <CardHorizontal
        :card="card"
    />
  </div>
</template>

<script>
import CardHorizontal from "@/components/CardHorizontal";

export default {
  name: "Bestseller",
  props: ["card"],
  components: {CardHorizontal},

}
</script>

<style scoped>
.sale-block {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>