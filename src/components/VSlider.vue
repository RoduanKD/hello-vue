<template>
  <!-- this is the old code we wrote during the session -->
  <!-- <ul>
    <li v-for="image in images" :key="image">
      <img :src="image" alt="">
    </li>
  </ul> -->
  <div class="slider">
    <button @click="previous">prev</button>
    <img :src="selectedImage" alt="" width="800">
    <button @click="next">next</button>
    <br>
    <button @click="clear">clear</button>
  </div>
</template>

<script>
export default {
  props: {
    images: {
      type: Array,
      // required: true,
      default: () => []
    }
  },
  data () {
    return {
      selectedIndex: 0
    }
  },
  computed: {
    selectedImage () {
      // return here the selected Image according to selected Index (remove null)
      return this.images[this.selectedIndex]
    }
  },
  methods: {
    previous () {
      // alter selected index to change selected image
      this.selectedIndex--
      if (this.selectedIndex === -1) { this.selectedIndex = this.images.length - 1 }
    },
    next () {
      // alter selected index to change selected image
      this.selectedIndex++
      if (this.selectedIndex === this.images.length) { this.selectedIndex = 0 }
    },
    clear () {
      // this.images = []
      this.$emit('clear-images', 'this is an argument')
    }
  }
}
</script>
