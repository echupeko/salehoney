<template>
  <v-app>
    <Header :navList="navList"/>
    <div class="content">
      <SliderPhoto/>
      <ContentBlock
          v-for="navItem in blockCreate"
          :navItem="navItem"
          :key="navItem.id"
      />
    </div>
  </v-app>
</template>

<script>
import Header from "@/components/Header";
import ContentBlock from "@/components/ContentBlock";
import SliderPhoto from "@/components/SliderPhoto";

export default {
  name: 'App',
  components: {
    SliderPhoto,
    ContentBlock,
    Header
  },
  data() {
    return {

      navList: [
        {id: 0, name: 'home', title: 'Главная', blockCreate: false},
        {id: 1, name: 'sale', title: 'Акции', blockCreate: true},
        {id: 2, name: 'catalog', title: 'Каталог', blockCreate: true},
        {id: 3, name: 'certificate', title: 'Сертификаты', blockCreate: true},
        {id: 4, name: 'about', title: 'О пасеке', blockCreate: true},
        {id: 5, name: 'contact', title: 'Контакты', blockCreate: true}
      ]
    }
  },
  computed: {
    blockCreate() {
      return this.navList.filter(item => item.blockCreate)
    }
  }
};
</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;600;700;800&display=swap');

body {
  padding: 0;
  margin: 0;
  font-family: 'Open Sans', sans-serif;
  box-sizing: content-box;
}

p, h1, h2, h3, h4 {
  margin: 0;
  padding: 0;
}

.content {
  position: relative;
  top: 119px;
  background-image: url("/resource/background-header.jpg");
  background-repeat: repeat;
}

.content > div {
  width: 100%;
}

*::-webkit-scrollbar {
  height: 10px;
}

*::-webkit-scrollbar-track {
  background-color: rgba(235, 166, 74, 0.48);
}

*::-webkit-scrollbar:vertical {
  width: 10px;
}

*::-webkit-scrollbar-thumb {
  -webkit-border-radius: 2px;
  background: #eba64a;
}

*::-webkit-scrollbar-button {
  height: 0;
  width: 0;
}

*::-webkit-scrollbar-thumb:window-inactive {
  background-color: #a19fa2;
  transition: background-color 3ms ease;
}
</style>
