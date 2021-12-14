<template>
  <button :style="style" @click="ghina">
    {{ message }}
  </button>
</template>

<script>
export default {
  props: [
    'message',
    'activeColor',
    'link'
  ],
  data () {
    return {
      count: 0,
      style: {
        backgroundColor: ''
      }
    }
  },
  methods: {
    ghina () {
      this.style.backgroundColor = this.activeColor
      if (this.link) {
        location.href = this.link
      }
    }
  }
}
</script>
