<template>
    <main :key="key">
        <img :src="gambar" alt="">
        <h3>{{hero.nama}}</h3>
        <p><em>{{hero.type}}</em></p>
  </main>
</template>

<script>
export default {
    props: ['hero', 'key'],
    computed: {
        gambar: function() {
        return require("../assets/hero/" + this.hero.gambar);
        }
    }
}
</script>

<style scoped>
    p {
        color: pink;
    }
</style>