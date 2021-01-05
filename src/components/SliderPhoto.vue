<template>
  <v-app>
    <v-carousel
        :interval=3000
        :continuous=false
        :multiple=false
        :show-arrows-on-hover="true"
        cycle
        hide-delimiter-background
        delimiter-icon="mdi-minus"
        color=success
    >
      <v-carousel-item
          v-for="item in carouselList"
          :key="item.id"
          :src="$srcCarousel + item.id + '.png'"
          reverse-transition="fade-transition"
          transition="fade-transition"
      >
        <div class="carousel-description">
          <h3>{{ item.title }}</h3>
          <p>{{item.description}}<p/>
        </div>
      </v-carousel-item>
    </v-carousel>
  </v-app>
</template>

<script>
export default {
  name: "SliderPhoto",
  data() {
    return {
      carouselList: [
        {
          id: 0,
          title: 'Наша большая семья',
          description: 'Количество семейств насчитывает больше десятка'
        },
        {
          id: 1,
          title: 'Алтайские пейзажи',
          description: 'Горная местность позволяет получать наивкуснейший и разнообразный мёд'
        },
        {
          id: 2,
          title: 'Сотовый мёд',
          description: 'Мы следим за своей продукцией'
        },
        {
          id: 3,
          title: 'Наша пасека',
          description: 'Даже медведи непрочь посетить нашу пасеку, но увы для них мёд не собираем'
        }
      ]
    }
  }
}
</script>

<style scoped>
.carousel-description {
  width: 100%;
  text-align: center;
  background-color: black;
  position: absolute;
  left: 0;
  bottom: 50px;
}
</style>