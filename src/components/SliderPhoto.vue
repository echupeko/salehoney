<template>
  <v-carousel
      :interval=3000
      :multiple=false
      :show-arrows-on-hover="true"
      cycle
      hide-delimiter-background
      delimiter-icon=""
      class="custom-carousel"
  >
    <v-carousel-item
        v-for="item in carouselList"
        :key="item.id"
        :src="$srcCarousel + item.id + '.png'"
        transition="fade-transition"
        reverse-transition="fade-transition"
    >
      <div class="carousel-description">
        <h3>{{ item.title }}</h3>
        <p>{{ item.description }}
        <p/>
      </div>
    </v-carousel-item>
  </v-carousel>
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

<style>
.v-carousel .v-window-item {
  position: absolute;
  top: 0;
  width: 100%;
}
.custom-carousel .v-carousel__controls__item.v-btn {
  color: transparent;
  width: 25px !important;
  height: 3px !important;
  margin: 0 4px;
  background-color: #FF9715 !important;
  border-radius: unset;
  opacity: 0.6;
}

.custom-carousel .v-carousel__controls__item.v-btn.v-btn--active {
  opacity: 1;
}

.custom-carousel .v-carousel__controls__item.v-btn.v-btn--active:before {
  opacity: 0 !important;
}

.custom-carousel .v-carousel__controls__item.v-btn:hover {
  background-color: white !important;
  opacity: 1;
}

.custom-carousel .v-carousel__controls__item.v-btn:hover:before {
  opacity: 0 !important;
}

.carousel-description {
  padding-top: 100px;
  height: 20%;
  width: 100%;
  text-align: center;
  background: linear-gradient(0deg, rgba(0, 0, 0, 1) 0%, rgba(255, 255, 255, 0) 100%);
  position: absolute;
  left: 0;
  bottom: 0;
}
</style>