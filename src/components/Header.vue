<template>
  <div class="main">
    <div class="logo"></div>
    <ul class="list">
      <MenuItem
          v-for="navItem in navList"
          :navItem="navItem"
          :key="navItem.id"
      />
    </ul>
    <Basket/>
  </div>
</template>

<script>
import MenuItem from "@/components/MenuItem";
import Basket from "@/components/Basket";

export default {
  name: 'Header',
  components: {Basket, MenuItem},
  props: ["navList"],
}
</script>

<style scoped>
.main {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  background-image: url("/resource/background-header.jpg");
  background-repeat: repeat;
  border-bottom: 2px #4e4c4c solid;
  box-shadow: 0 0 25px black inset ;
}

.logo {
  min-width: 160px;
  min-height: 93px;
  border: 2px solid #4e4c4c;
  background-image: url("/resource/logo.jpg");
  background-size: cover;
  margin: 10px;
}

.list {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  list-style: none;
  margin: 0;
  padding: 0;
}

</style>
