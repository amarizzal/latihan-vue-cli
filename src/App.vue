<template>
<div>

  <Header @ganti-hero="gantiHero"></Header>

  <Hero v-for="(item, key) of hero" :hero="item" :key="key"></Hero>

  <Footer></Footer>
  
</div>
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Hero from './components/Hero.vue';

export default {
  name: 'App',
  components: {
    Header,
    Hero,
    Footer
  },
  data: function() {
    return {
      hero: [{
        nama: 'Aurora',
        type: 'Mage',
        gambar: 'aurora.jpg'
      },
      {
        nama: 'Akai',
        type: 'Tank',
        gambar: 'akai.jpg'
      }
      ]}
  },
  methods: {
    gantiHero: function() {
      this.hero.nama = "Zilong";
      this.hero.type = "Fighter";
      this.hero.gambar = "zilong.jpg";
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
