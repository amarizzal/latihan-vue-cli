<template>
<div>

  <Header></Header>

  <main>
    <img :src="gambar" alt="">
    <h3>{{hero.nama}}</h3>
    <p><em>{{hero.type}}</em></p>
  </main>

  <Footer></Footer>
  
</div>
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    Footer
  },
  data: function() {
    return {
      hero: {
        nama: 'Aurora',
        type: 'Mage',
        gambar: 'aurora.jpg'
      }
    }
  },
  computed: {
    gambar: function() {
      return require("./assets/hero/" + this.hero.gambar);
    }
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
