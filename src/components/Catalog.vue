<template>
  <div>
    <div class="container-card">
      <CardVertical
          v-for="card in this.$catalogList"
          :card="card"
          :key="card.id"
      />
    </div>
  </div>
</template>

<script>
import CardVertical from "@/components/CardVertical";
export default {
  name: "Catalog",
  components: {CardVertical}
}
</script>

<style scoped>
.container-card {
  display: flex;
  flex-direction:row;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
</style>