<template>
  <div class="button" @click="$emit('click')">{{ title }}</div>
</template>

<script>
export default {
  name: "Button",
  props: ["title"]
}
</script>

<style scoped>
.button {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
  border-radius: 50px;
  background-color: rgb(255, 220, 0);
  color: #61341f;
  cursor: pointer;
}
</style>