<template>
<div>

  <Header @random-hero="randomHero" @reset-hero="resetHero"></Header>

  <article v-if="!selectedHero">
    <Hero v-for="(item, key) of hero" :hero="item" :key="key"></Hero>
  </article>
  <article v-else>
    <Hero :hero="selectedHero" :key="0"></Hero>
  </article>

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
      },
      {
        nama: 'Zilong',
        type: 'Fighter',
        gambar: 'zilong.jpg'
      },
      {
        nama: 'Layla',
        type: 'Marksman',
        gambar: 'layla.jpg'
      },
      {
        nama: 'Gatotkaca',
        type: 'Tank',
        gambar: 'gatotkaca.png'
      }],
      selectedHero: ''
  }},
  methods: {
    randomHero: function() {
      this.selectedHero = this.hero[Math.floor(Math.random() * this.hero.length)];
    },
    resetHero: function() {
      this.selectedHero = '';
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

article {
  display: flex;
  justify-content: center;
}

main {
  margin: 10px;
}
</style>
