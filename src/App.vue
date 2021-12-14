<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <v-button message="accept" activeColor="green" link="https://google.com"></v-button>
    <v-button message="delete" activeColor="red"></v-button>
    <v-button message="select" activeColor="blue"></v-button>
    <v-button message="edit" activeColor="yellow"></v-button>
    <HelloWorld msg="Welcome to our Frontend Course"/>
    <v-slider images="images" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import VButton from './components/VButton.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    VButton
  },
  data () {
    return {
      images: []
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
