<template>
  <div class="form">
    <h3>Ваша корзина пуста</h3>
    <BasketItem
        v-for="honey in basketArrayLocal"
        :honey="honey"
        :key="honey.id"
    />
  </div>
</template>

<script>
import BasketItem from "@/components/BasketItem";

export default {
  name: "BasketForm",
  data() {
    return {
      basketArrayLocal: []
    }
  },
  components: {BasketItem},
  mounted() {
    this.basketArrayLocal = this.$basketArray;
  }
}
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: absolute;
  top: 140px;
  right: 20px;

  border-radius: 25px;
  border: 1px solid white;
  padding: 25px;
  backdrop-filter: blur(3px);

  /*стекломорфизм*/
  background: linear-gradient(25deg, rgba(255,255,255,0.4) 30%, rgba(255,255,255,0.7) 70%);
  box-shadow: 0 0 25px rgba(0,0,0,0.8);

  /*неоморфизм*/
  /*background-color: #f9f9f9;*/
  /*box-shadow:  5px 5px 5px rgba(0,0,0,0.6),*/
  /*             -5px -5px 5px rgba(229, 229, 229, 0.8);*/
  }

</style>