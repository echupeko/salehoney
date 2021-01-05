<template>
  <li :class="navItem.name">
    <a :href="'#'+navItem.name">{{ navItem.title }}</a>
  </li>
</template>

<script>
export default {
  name: "MenuItem",
  props: ["navItem"]
}
</script>

<style scoped>
li {
  position: relative;
  border-radius: 10px;
  margin: 0 10px;
  background-color: rgba(255, 255, 255, 0.64);
  cursor: pointer;
  transition: all .3s ease-in-out;
  padding: 5px 0;
}

a {
  font-weight: bold;
  padding: 5px 10px;
  background-color: #61341f;
  font-size: 20px;
  text-decoration: none;
  -webkit-text-fill-color: transparent;
  -webkit-background-clip: text;
}

li:hover {
  background-color: white;
}

.sale {
  background-color: rgba(255, 220, 0, 0.8);

}

.sale:hover {
  background-color: rgb(255, 220, 0);
}

.sale:after {
  display: block;
  width: 50px;
  height: 25px;
  position: absolute;
  top: 25px;
  right: -27px;
  content: '';
  transform: rotateZ(15deg);
  transform-origin: 0 100%;
  animation: rotate .9s ease-in-out infinite;
  background-image: url("/resource/sale.png");
  background-repeat: no-repeat;
  background-size: contain;
  z-index: 1100;
}

@keyframes rotate {
  0% {transform:rotate(15deg)}
  50%{transform:rotate(20deg)}
  100%{transform:rotate(15deg)}}
</style>