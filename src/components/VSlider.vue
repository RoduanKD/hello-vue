<template>
  <!-- this is the old code we wrote during the session -->
  <!-- <ul>
    <li v-for="image in images" :key="image">
      <img :src="image" alt="">
    </li>
  </ul> -->
  <div class="slider">
    <button @click="previous">prev</button>
    <img :src="selectedImage" alt="">
    <button @click="next">next</button>
  </div>
</template>

<script>
export default {
  props: ['images'],
  data () {
    return {
      selectedIndex: 0
    }
  },
  computed: {
    selectedImage () {
      // return here the selected Image according to selected Index (remove null)
      return null
    }
  },
  methods: {
    previous () {
      // alter selected index to change selected image
    },
    next () {
      // alter selected index to change selected image
    }
  }
}
</script>
