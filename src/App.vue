<template>
<div>
  <img alt="Vue logo" src="./assets/logo.png">

  <header>
    <h1>Mobile Legend</h1>
  </header>

  <main>
    <img :src="gambar" alt="">
    <h3>{{hero.nama}}</h3>
  </main>

  <footer>
    copyright 2021 - Rizal Ammar
  </footer>
</div>
</template>

<script>

export default {
  name: 'App',
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
      return require("./assets/hero" + this.hero.gambar);
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
