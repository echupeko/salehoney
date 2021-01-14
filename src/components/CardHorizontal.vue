<template>
  <div class="card">
    <img :src="this.$srcHoney + card.title + '.jpg'" alt="картинка">
    <div class="card-body">
      <h3>Мёд {{ card.title }} {{ card.count }}л.</h3>
      <div>
        <div class="crossOut"><span></span>
          <h4>{{ card.price }} руб.</h4>
        </div>
        <h2>{{ card.salePrice }} руб.</h2>
      </div>
      <div class="button-block">
        <Button
            :title="'Добавить в корзину'"
        />
        <small>прочитать об этом виде мёда</small>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "@/components/Button";

export default {
  name: "CardHorizontal",
  components: {Button},
  props: ["card"],
  data() {
    return {
      catalog: this.$catalogList
    }
  }
}
</script>

<style scoped>
.card {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  width: 500px;
  height: 200px;
  overflow: auto;
  background-color: rgba(255, 255, 255, 0.8);
  border-radius: 50px 15px;
  border: 3px solid #4e4c4c;
}

h2, h4 {
  font-weight: normal;
}

h4{
  white-space:pre;
  position:relative;
  display:inline-block;
  font-size:20px;
}
h4:after{
  content:"";
  display:block;
  position:absolute;
  left:0;top:50%;
  color:red;
  width:100%;
  height:0;
  border-bottom:2px solid red;
  transform:rotate(15deg);
}

img {
  width: 200px;
  height: 100%;
  border-radius: 0 0 50px 0;
}

.card-body {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: flex-start;
  width: 500px;
  height: 100%;
  padding-left: 20px;
}

small {
  font-size: 80%;
  color: #808080;
}
</style>