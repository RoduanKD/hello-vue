<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <v-slider :images="images" @clear-images="clear" @add-image="addImage" />
    <data-table :items="users" :headers="headers" @deleteSelectedItem="deleteItem">
      <div class="style">this is where fathi can use the default slot</div>
      <img :src="images[0]" width="50" alt="">

      <template #name="{item}">
        {{ item.split('').reverse().join('').toUpperCase() }}
      </template>

      <template #birthdate="{item}">
        <span v-if="item <= 1996">10</span>
        <span v-else>{{item}}</span>
      </template>

      <!-- <template slot="footer">
        <h5>please make sure to cover something</h5>
      </template> -->
    </data-table>
  </div>
</template>

<script>
import DataTable from './components/DataTable.vue'
import VSlider from './components/VSlider.vue'
// import HelloWorld from './components/HelloWorld.vue'
// import VSlider here.

export default {
  name: 'App',
  components: {
    // import VSlider here Also.
    VSlider,
    DataTable
  },
  data () {
    return {
      images: [
        'https://wallpapercave.com/wp/wp3695039.jpg',
        'https://cdn.shopify.com/s/files/1/0017/0432/9285/files/programming-quotes-for-developers-made4dev-programmer-author.jpg?v=1539287556',
        'https://talgroupinc.files.wordpress.com/2017/04/programmers_april18.png?w=768'
      ],
      headers: [
        'name',
        'birthdate',
        'city'
      ],
      users: [
        {
          name: 'Mouayad',
          birthdate: 1997,
          city: 'Damascus'
        },
        {
          name: 'Mhd',
          birthdate: 1996,
          city: 'Damascus'
        },
        {
          name: 'Nour',
          birthdate: 1991,
          city: 'Damascus'
        }
      ]
    }
  },
  methods: {
    clear (fathi) {
      console.log(fathi)
      this.images = []
    },

    addImage (image) {
      this.images.push(image)
    },

    deleteItem (selectedItem) {
      if (confirm('are you sure you want to delete the selected user')) {
        // find & remove selected user from users array
        this.users.splice(this.users.findIndex(user => user.name === selectedItem), 1)
      }
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

.style {
  color:red;
}
</style>
