<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <v-slider :images="images" @clear-images="clear" />
  </div>
</template>

<script>
import VSlider from './components/VSlider.vue'
// import HelloWorld from './components/HelloWorld.vue'
// import VSlider here.

export default {
  name: 'App',
  components: {
    // import VSlider here Also.
    VSlider
  },
  data () {
    return {
      images: [
        'https://wallpapercave.com/wp/wp3695039.jpg',
        'https://cdn.shopify.com/s/files/1/0017/0432/9285/files/programming-quotes-for-developers-made4dev-programmer-author.jpg?v=1539287556',
        'https://talgroupinc.files.wordpress.com/2017/04/programmers_april18.png?w=768'
      ]
    }
  },
  methods: {
    clear (fathi) {
      console.log(fathi)
      this.images = []
    }
  }
}
</script>

<style>
#app {
  font-family: Cairo, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
